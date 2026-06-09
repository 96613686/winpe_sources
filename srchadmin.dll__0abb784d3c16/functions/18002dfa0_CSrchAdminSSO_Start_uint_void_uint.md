# CSrchAdminSSO::Start(uint,void * *,uint *)

- ea: `0x18002dfa0`
- end: `0x18002e186`
- name: `?Start@CSrchAdminSSO@@UEAAJIPEAPEAXPEAI@Z`
- size: `486`
- prototype: `__int64 __fastcall(CSrchAdminSSO *__hidden this, unsigned int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callees

- `0x18000d4dc`
- `0x18002c5b4`
- `0x18002dc3c`
- `0x18002dec0`
- `0x18002dfa0`
- `0x18002ec3c`
- `0x180032010`

## import_xrefs

- `SHLWAPI!__imp_SHQueueUserWorkItem` at `0x18002e020`
- `SHLWAPI!__imp_SHQueueUserWorkItem` at `0x18002e020`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e0f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e0f6`

## string_xrefs

- `0x18002e0b5`: `CscService`

## pseudocode

```c
__int64 __fastcall CSrchAdminSSO::Start(CSrchAdminSSO *this, unsigned int a2, void **a3, unsigned int *a4)
{
  char *v4; // rsi
  const unsigned __int16 *v9; // rdx
  HKEY v10; // rcx
  const unsigned __int16 *v11; // r8
  unsigned int v12; // r9d
  HWND v13; // rdx
  HWND WorkerWindow; // rax
  int Error; // edi
  CSrchAdminSSO *v16; // rcx
  unsigned int i; // esi
  struct CSrchAdminSSO::EVENT_HANDLER *EventW; // rax
  unsigned __int64 v19; // r14
  int v21; // [rsp+70h] [rbp+8h] BYREF

  v4 = (char *)this - 16;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 2) + 8LL))((char *)this - 16);
  v21 = 0;
  if ( (int)SHRegGetBOOLWithREGSAM(v10, v9, v11, v12, &v21) < 0 || !v21 )
    SHQueueUserWorkItem(CSrchAdminSSO::s_ReindexProfile, 0, 0, 0, 0, 0, 16);
  WorkerWindow = CImpWorkerWndProc::CreateWorkerWindow((CSrchAdminSSO *)((char *)this + 8), v13);
  *((_QWORD *)this + 2) = WorkerWindow;
  if ( WorkerWindow
    || (Error = ResultFromKnownLastError(), (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4), Error >= 0) )
  {
    *((_QWORD *)this + 21) = *((_QWORD *)this + 2);
    *((_DWORD *)this + 40) = 33792;
    *((_DWORD *)this + 41) = 33793;
    *((_QWORD *)this + 35) = *((_QWORD *)this + 2);
    *((_DWORD *)this + 68) = 33794;
    *((_DWORD *)this + 69) = 33795;
    Error = CServiceMonitorBase::InitializeServiceListening((CSrchAdminSSO *)((char *)this + 64), L"WSearch");
    if ( Error >= 0 )
    {
      if ( (unsigned int)CSrchAdminSSO::_IsCscServiceEnabled(v16)
        || (Error = CServiceMonitorBase::InitializeServiceListening(
                      (CSrchAdminSSO *)((char *)this + 176),
                      L"CscService"),
            Error >= 0) )
      {
        *((_DWORD *)this + 75) = 1;
        for ( i = 0; i < 2; ++i )
        {
          if ( *a4 >= a2 )
            break;
          EventW = (struct CSrchAdminSSO::EVENT_HANDLER *)CreateEventW(0, 1, 0, 0);
          v19 = 32LL * i;
          *(struct CSrchAdminSSO::EVENT_HANDLER near **)((char *)&CSrchAdminSSO::_rgEvtHandlers + v19) = EventW;
          if ( !EventW )
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
              break;
          }
          Error = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, __int64 *))((char *)&CSrchAdminSSO::_rgEvtHandlers
                                                                               + v19
                                                                               + 8))(
                    (char *)this + *(int *)((char *)&CSrchAdminSSO::_rgEvtHandlers + v19 + 16) - 16,
                    *(struct CSrchAdminSSO::EVENT_HANDLER near **)((char *)&CSrchAdminSSO::_rgEvtHandlers + v19),
                    0,
                    &qword_180041338[v19 / 8]);
          if ( Error < 0 )
            break;
          a3[(*a4)++] = *(struct CSrchAdminSSO::EVENT_HANDLER near **)((char *)&CSrchAdminSSO::_rgEvtHandlers + v19);
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002dfa0  mov     [rsp+arg_8], rbx
0x18002dfa5  mov     [rsp+arg_10], rbp
0x18002dfaa  push    rsi
0x18002dfab  push    rdi
0x18002dfac  push    r12
0x18002dfae  push    r14
0x18002dfb0  push    r15
0x18002dfb2  sub     rsp, 40h
0x18002dfb6  lea     rsi, [rcx-10h]
0x18002dfba  mov     rbx, rcx
0x18002dfbd  mov     rax, [rsi]
0x18002dfc0  mov     rcx, rsi
0x18002dfc3  mov     rbp, r9
0x18002dfc6  mov     r12, r8
0x18002dfc9  mov     r15d, edx
0x18002dfcc  mov     rax, [rax+8]
0x18002dfd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfd5  lea     rax, [rsp+68h+arg_0]
0x18002dfda  mov     [rsp+68h+arg_0], 0
0x18002dfe2  mov     [rsp+68h+var_48], rax; int *
0x18002dfe7  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18002dfec  test    eax, eax
0x18002dfee  js      short loc_18002DFF7
0x18002dff0  cmp     [rsp+68h+arg_0], 0
0x18002dff5  jnz     short loc_18002E026
0x18002dff7  mov     [rsp+68h+var_38], 10h
0x18002dfff  lea     rcx, ?s_ReindexProfile@CSrchAdminSSO@@CAKPEAX@Z; CSrchAdminSSO::s_ReindexProfile(void *)
0x18002e006  mov     [rsp+68h+var_40], 0
0x18002e00f  xor     r9d, r9d
0x18002e012  xor     r8d, r8d
0x18002e015  mov     [rsp+68h+var_48], 0; HMENU
0x18002e01e  xor     edx, edx
0x18002e020  call    cs:__imp_SHQueueUserWorkItem
0x18002e026  lea     rcx, [rbx+8]; this
0x18002e02a  call    ?CreateWorkerWindow@CImpWorkerWndProc@@IEAAPEAUHWND__@@PEAU2@KKPEAUHMENU__@@@Z; CImpWorkerWndProc::CreateWorkerWindow(HWND__ *,ulong,ulong,HMENU__ *)
0x18002e02f  mov     [rbx+10h], rax
0x18002e033  test    rax, rax
0x18002e036  jnz     short loc_18002E056
0x18002e038  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002e03d  mov     rdx, [rsi]
0x18002e040  mov     edi, eax
0x18002e042  mov     rcx, rsi
0x18002e045  mov     rax, [rdx+10h]
0x18002e049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e04e  test    edi, edi
0x18002e050  js      loc_18002E16B
0x18002e056  mov     rax, [rbx+10h]
0x18002e05a  lea     rcx, [rbx+40h]; this
0x18002e05e  mov     [rcx+68h], rax
0x18002e062  lea     rdx, ServiceName; "WSearch"
0x18002e069  mov     dword ptr [rcx+60h], 8400h
0x18002e070  mov     dword ptr [rcx+64h], 8401h
0x18002e077  mov     rax, [rbx+10h]
0x18002e07b  mov     [rbx+118h], rax
0x18002e082  mov     dword ptr [rbx+110h], 8402h
0x18002e08c  mov     dword ptr [rbx+114h], 8403h
0x18002e096  call    ?InitializeServiceListening@CServiceMonitorBase@@QEAAJPEBG@Z; CServiceMonitorBase::InitializeServiceListening(ushort const *)
0x18002e09b  mov     edi, eax
0x18002e09d  test    eax, eax
0x18002e09f  js      loc_18002E16B
0x18002e0a5  call    ?_IsCscServiceEnabled@CSrchAdminSSO@@AEAAJXZ; CSrchAdminSSO::_IsCscServiceEnabled(void)
0x18002e0aa  test    eax, eax
0x18002e0ac  jnz     short loc_18002E0CB
0x18002e0ae  lea     rcx, [rbx+0B0h]; this
0x18002e0b5  lea     rdx, aCscservice; "CscService"
0x18002e0bc  call    ?InitializeServiceListening@CServiceMonitorBase@@QEAAJPEBG@Z; CServiceMonitorBase::InitializeServiceListening(ushort const *)
0x18002e0c1  mov     edi, eax
0x18002e0c3  test    eax, eax
0x18002e0c5  js      loc_18002E16B
0x18002e0cb  mov     dword ptr [rbx+12Ch], 1
0x18002e0d5  xor     esi, esi
0x18002e0d7  cmp     esi, 2
0x18002e0da  jnb     loc_18002E16B
0x18002e0e0  cmp     [rbp+0], r15d
0x18002e0e4  jnb     loc_18002E16B
0x18002e0ea  xor     r9d, r9d; lpName
0x18002e0ed  xor     r8d, r8d; bInitialState
0x18002e0f0  xor     ecx, ecx; lpEventAttributes
0x18002e0f2  lea     edx, [r9+1]; bManualReset
0x18002e0f6  call    cs:__imp_CreateEventW
0x18002e0fc  mov     r14d, esi
0x18002e0ff  lea     r10, ?_rgEvtHandlers@CSrchAdminSSO@@0PAUEVENT_HANDLER@1@A; CSrchAdminSSO::EVENT_HANDLER near * CSrchAdminSSO::_rgEvtHandlers
0x18002e106  shl     r14, 5
0x18002e10a  mov     [r14+r10], rax
0x18002e10e  test    rax, rax
0x18002e111  jnz     short loc_18002E125
0x18002e113  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002e118  mov     edi, eax
0x18002e11a  test    eax, eax
0x18002e11c  js      short loc_18002E16B
0x18002e11e  lea     r10, ?_rgEvtHandlers@CSrchAdminSSO@@0PAUEVENT_HANDLER@1@A; CSrchAdminSSO::EVENT_HANDLER near * CSrchAdminSSO::_rgEvtHandlers
0x18002e125  movsxd  rcx, dword ptr [r14+r10+10h]
0x18002e12a  lea     r9, [r10+18h]
0x18002e12e  mov     rdx, [r14+r10]
0x18002e132  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18002e136  mov     rax, [r14+r10+8]
0x18002e13b  add     rcx, rbx
0x18002e13e  add     r9, r14
0x18002e141  xor     r8d, r8d
0x18002e144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e149  mov     edi, eax
0x18002e14b  test    eax, eax
0x18002e14d  js      short loc_18002E16B
0x18002e14f  mov     ecx, [rbp+0]
0x18002e152  lea     rax, ?_rgEvtHandlers@CSrchAdminSSO@@0PAUEVENT_HANDLER@1@A; CSrchAdminSSO::EVENT_HANDLER near * CSrchAdminSSO::_rgEvtHandlers
0x18002e159  mov     rax, [r14+rax]
0x18002e15d  mov     [r12+rcx*8], rax
0x18002e161  inc     dword ptr [rbp+0]
0x18002e164  inc     esi
0x18002e166  jmp     loc_18002E0D7
0x18002e16b  lea     r11, [rsp+68h+var_28]
0x18002e170  mov     eax, edi
0x18002e172  mov     rbx, [r11+38h]
0x18002e176  mov     rbp, [r11+40h]
0x18002e17a  mov     rsp, r11
0x18002e17d  pop     r15
0x18002e17f  pop     r14
0x18002e181  pop     r12
0x18002e183  pop     rdi
0x18002e184  pop     rsi
0x18002e185  retn
```
