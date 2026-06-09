# DeviceObject::DoesDeviceExist(ushort const *,bool *)

- ea: `0x180015014`
- end: `0x1800151db`
- name: `?DoesDeviceExist@DeviceObject@@SAJPEBGPEA_N@Z`
- size: `455`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004bf4`

## callees

- `0x1800133bc`
- `0x180013acc`
- `0x180014974`
- `0x180015014`
- `0x1800153c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015158`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015158`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015087`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001517b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001517b`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800151a6`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800151a6`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQueryFromId` at `0x180015134`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQueryFromId` at `0x180015134`

## pseudocode

```c
__int64 __fastcall DeviceObject::DoesDeviceExist(const unsigned __int16 *a1, bool *a2)
{
  unsigned __int16 near **v2; // rbx
  signed int ObjectQueryFromId; // edi
  int v5; // eax
  __int64 v6; // rsi
  HANDLE EventW; // rax
  signed int LastError; // eax
  DWORD v9; // eax
  signed int v10; // eax
  NCoreLibrary::TString *v11; // rcx
  __int64 v13; // [rsp+98h] [rbp+28h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+30h]

  v2 = &NCoreLibrary::TString::gszNullState;
  if ( a2 )
  {
    *a2 = 0;
    v13 = (__int64)&NCoreLibrary::TString::gszNullState;
    v5 = NCoreLibrary::TString::Format((NCoreLibrary::TString *)&v13, L"SWD\\PRINTENUM\\%ws", a1);
    v2 = (unsigned __int16 near **)v13;
    ObjectQueryFromId = v5;
  }
  else
  {
    ObjectQueryFromId = -2147024809;
  }
  v13 = -1;
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&v13);
  v6 = -1;
  v13 = -1;
  if ( ObjectQueryFromId >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    NCoreLibrary::TAutoHandleNT::operator=(&v13, EventW);
    v6 = v13;
    if ( v13 == -1 )
    {
      LastError = GetLastError();
      ObjectQueryFromId = LastError;
      if ( LastError > 0 )
        ObjectQueryFromId = (unsigned __int16)LastError | 0x80070000;
    }
  }
  v14 = 0;
  if ( ObjectQueryFromId >= 0 )
  {
    ObjectQueryFromId = DevCreateObjectQueryFromId(3, v2, 0);
    if ( ObjectQueryFromId >= 0 )
    {
      if ( v6 == -1 )
        v6 = 0;
      v9 = WaitForSingleObject((HANDLE)v6, 0xFFFFFFFF);
      if ( v9 )
      {
        if ( v9 == -1 )
        {
          v10 = GetLastError();
          ObjectQueryFromId = v10;
          if ( v10 > 0 )
            ObjectQueryFromId = (unsigned __int16)v10 | 0x80070000;
        }
        else
        {
          ObjectQueryFromId = -2147418113;
        }
      }
      else
      {
        ObjectQueryFromId = 0;
        *a2 = 0;
      }
    }
    if ( v14 )
      DevCloseObjectQuery();
  }
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&v13);
  NCoreLibrary::TString::vFree(v11, v2);
  return (unsigned int)ObjectQueryFromId;
}

```

## disassembly

```asm
0x180015014  mov     [rsp-18h+arg_0], rbx
0x180015019  mov     [rsp-18h+arg_18], rsi
0x18001501e  push    rbp
0x18001501f  push    rdi
0x180015020  push    r14
0x180015022  mov     rbp, rsp
0x180015025  sub     rsp, 70h
0x180015029  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180015030  mov     r14, rdx
0x180015033  test    rdx, rdx
0x180015036  jnz     short loc_18001503F
0x180015038  mov     edi, 80070057h
0x18001503d  jmp     short loc_18001505F
0x18001503f  mov     byte ptr [rdx], 0
0x180015042  mov     r8, rcx
0x180015045  lea     rdx, aSwdPrintenumWs; "SWD\\PRINTENUM\\%ws"
0x18001504c  mov     [rbp+arg_8], rbx
0x180015050  lea     rcx, [rbp+arg_8]; this
0x180015054  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x180015059  mov     rbx, [rbp+arg_8]
0x18001505d  mov     edi, eax
0x18001505f  lea     rcx, [rbp+arg_8]
0x180015063  mov     [rbp+arg_8], 0FFFFFFFFFFFFFFFFh
0x18001506b  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x180015070  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180015074  mov     [rbp+arg_8], rsi
0x180015078  test    edi, edi
0x18001507a  js      short loc_1800150C4
0x18001507c  xor     r9d, r9d; lpName
0x18001507f  lea     edx, [rsi+2]; bManualReset
0x180015082  xor     r8d, r8d; bInitialState
0x180015085  xor     ecx, ecx; lpEventAttributes
0x180015087  call    cs:__imp_CreateEventW
0x18001508e  nop     dword ptr [rax+rax+00h]
0x180015093  mov     rdx, rax
0x180015096  lea     rcx, [rbp+arg_8]
0x18001509a  call    ??4TAutoHandleNT@NCoreLibrary@@QEAAPEAXPEAX@Z; NCoreLibrary::TAutoHandleNT::operator=(void *)
0x18001509f  mov     rsi, [rbp+arg_8]
0x1800150a3  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800150a7  jnz     short loc_1800150C4
0x1800150a9  call    cs:__imp_GetLastError
0x1800150b0  nop     dword ptr [rax+rax+00h]
0x1800150b5  mov     edi, eax
0x1800150b7  test    eax, eax
0x1800150b9  jle     short loc_1800150C4
0x1800150bb  movzx   edi, ax
0x1800150be  or      edi, 80070000h
0x1800150c4  xor     eax, eax
0x1800150c6  xorps   xmm0, xmm0
0x1800150c9  mov     [rbp+var_10], rax
0x1800150cd  mov     [rbp+arg_10], rax
0x1800150d1  movups  [rbp+var_20], xmm0
0x1800150d5  test    edi, edi
0x1800150d7  js      loc_1800151B2
0x1800150dd  mov     dword ptr [rbp+var_10], eax
0x1800150e0  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800150e4  mov     rcx, rsi
0x1800150e7  mov     rdx, rbx
0x1800150ea  cmovz   rcx, rax
0x1800150ee  lea     rax, [rbp+arg_10]
0x1800150f2  mov     [rsp+70h+var_28], rax
0x1800150f7  xor     r9d, r9d
0x1800150fa  lea     rax, [rbp+var_20]
0x1800150fe  mov     qword ptr [rbp+var_20+8], rcx
0x180015102  mov     [rsp+70h+var_30], rax
0x180015107  xor     r8d, r8d
0x18001510a  lea     rax, ?DeviceQueryCallback@DeviceObject@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; DeviceObject::DeviceQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180015111  mov     [rsp+70h+var_38], rax
0x180015116  lea     ecx, [r9+3]
0x18001511a  mov     [rsp+70h+var_40], 0
0x180015123  mov     [rsp+70h+var_48], 0
0x18001512b  mov     [rsp+70h+var_50], 0
0x180015134  call    cs:__imp_DevCreateObjectQueryFromId
0x18001513b  nop     dword ptr [rax+rax+00h]
0x180015140  mov     edi, eax
0x180015142  test    eax, eax
0x180015144  js      short loc_18001519D
0x180015146  xor     eax, eax
0x180015148  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001514c  cmovz   rsi, rax
0x180015150  or      edi, 0FFFFFFFFh
0x180015153  mov     edx, edi; dwMilliseconds
0x180015155  mov     rcx, rsi; hHandle
0x180015158  call    cs:__imp_WaitForSingleObject
0x18001515f  nop     dword ptr [rax+rax+00h]
0x180015164  test    eax, eax
0x180015166  jnz     short loc_180015177
0x180015168  mov     edi, dword ptr [rbp+var_10]
0x18001516b  test    edi, edi
0x18001516d  js      short loc_18001519D
0x18001516f  mov     al, byte ptr [rbp+var_20]
0x180015172  mov     [r14], al
0x180015175  jmp     short loc_18001519D
0x180015177  cmp     eax, edi
0x180015179  jnz     short loc_180015198
0x18001517b  call    cs:__imp_GetLastError
0x180015182  nop     dword ptr [rax+rax+00h]
0x180015187  mov     edi, eax
0x180015189  test    eax, eax
0x18001518b  jle     short loc_18001519D
0x18001518d  movzx   edi, ax
0x180015190  or      edi, 80070000h
0x180015196  jmp     short loc_18001519D
0x180015198  mov     edi, 8000FFFFh
0x18001519d  mov     rcx, [rbp+arg_10]
0x1800151a1  test    rcx, rcx
0x1800151a4  jz      short loc_1800151B2
0x1800151a6  call    cs:__imp_DevCloseObjectQuery
0x1800151ad  nop     dword ptr [rax+rax+00h]
0x1800151b2  lea     rcx, [rbp+arg_8]
0x1800151b6  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x1800151bb  mov     rdx, rbx; void *
0x1800151be  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x1800151c3  lea     r11, [rsp+70h+var_s0]
0x1800151c8  mov     eax, edi
0x1800151ca  mov     rbx, [r11+20h]
0x1800151ce  mov     rsi, [r11+38h]
0x1800151d2  mov     rsp, r11
0x1800151d5  pop     r14
0x1800151d7  pop     rdi
0x1800151d8  pop     rbp
0x1800151d9  retn
```
