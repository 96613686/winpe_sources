# OpenWerStore<&WerpOpenMachineQueue(void * *)>(IWerStore * *)

- ea: `0x180008420`
- end: `0x18000862f`
- name: `??$OpenWerStore@$1?WerpOpenMachineQueue@@YAJPEAPEAX@Z@@YAJPEAPEAUIWerStore@@@Z`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000b050`

## callees

- `0x180001634`
- `0x180002850`
- `0x180006c9c`
- `0x1800073d4`
- `0x180008420`
- `0x18000bcfc`
- `0x180013010`

## import_xrefs

- `wer!WerpCloseStore` at `0x1800085f3`
- `wer!WerpCloseStore` at `0x180008617`
- `wer!WerpCloseStore` at `0x1800085f3`
- `wer!WerpCloseStore` at `0x180008617`
- `wer!WerpOpenMachineQueue` at `0x180008485`
- `wer!WerpOpenMachineQueue` at `0x180008485`

## pseudocode

```c
__int64 __fastcall OpenWerStore<&long WerpOpenMachineQueue(void * *)>(__int64 a1)
{
  CManagedObj *v1; // rbx
  int v3; // edi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  CManagedObj *v6; // rax
  __int64 v7; // rcx
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v9 = 0;
  if ( !a1 )
  {
    v3 = -2147467259;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    goto LABEL_24;
  }
  v3 = WerpOpenMachineQueue(&v9);
  if ( v3 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_24;
    v5 = 99;
    goto LABEL_9;
  }
  v6 = (CManagedObj *)operator new(0x30u);
  v1 = v6;
  if ( v6 )
  {
    CManagedObj::CManagedObj(v6);
    *((_DWORD *)v1 + 10) = 0;
    *(_QWORD *)v1 = &CWerComStore::`vftable'{for `CManagedObj'};
    *((_QWORD *)v1 + 3) = &CWerComStore::`vftable'{for `IWerStore'};
    *((_QWORD *)v1 + 4) = 0;
    _InterlockedIncrement((volatile signed __int32 *)v1 + 2);
    v10 = v9;
    v9 = 0;
    v3 = CWerComStore::Init(v1, &v10);
    if ( v3 < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v5 = 101;
LABEL_9:
      WPP_SF_d(v4[2], v5, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, (unsigned int)v3);
      goto LABEL_24;
    }
    v3 = (**(__int64 (__fastcall ***)(CManagedObj *, GUID *, __int64))v1)(v1, &IID_IWerStore, a1);
    if ( v3 >= 0 )
    {
      v3 = 0;
      goto LABEL_24;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 102;
      goto LABEL_9;
    }
  }
  else
  {
    v3 = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    v1 = 0;
  }
LABEL_24:
  v7 = v9;
  v9 = 0;
  if ( v7 )
    WerpCloseStore();
  if ( v1 )
    (*(void (__fastcall **)(CManagedObj *))(*(_QWORD *)v1 + 16LL))(v1);
  if ( v9 )
    WerpCloseStore();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008420  mov     [rsp+arg_10], rbx
0x180008425  mov     [rsp+arg_18], rsi
0x18000842a  push    rdi
0x18000842b  sub     rsp, 20h
0x18000842f  xor     ebx, ebx
0x180008431  mov     [rsp+28h+arg_0], 0
0x18000843a  mov     rsi, rcx
0x18000843d  test    rcx, rcx
0x180008440  jnz     short loc_180008480
0x180008442  mov     edi, 80004005h
0x180008447  mov     rcx, cs:WPP_GLOBAL_Control
0x18000844e  lea     rax, WPP_GLOBAL_Control
0x180008455  cmp     rcx, rax
0x180008458  jz      loc_1800085E0
0x18000845e  test    byte ptr [rcx+1Ch], 1
0x180008462  jz      loc_1800085E0
0x180008468  mov     rcx, [rcx+10h]
0x18000846c  lea     edx, [rsi+62h]
0x18000846f  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180008476  call    WPP_SF_
0x18000847b  jmp     loc_1800085E0
0x180008480  lea     rcx, [rsp+28h+arg_0]
0x180008485  call    cs:__imp_WerpOpenMachineQueue
0x18000848b  mov     edi, eax
0x18000848d  test    eax, eax
0x18000848f  jns     short loc_1800084CF
0x180008491  mov     rcx, cs:WPP_GLOBAL_Control
0x180008498  lea     rax, WPP_GLOBAL_Control
0x18000849f  cmp     rcx, rax
0x1800084a2  jz      loc_1800085E0
0x1800084a8  test    byte ptr [rcx+1Ch], 1
0x1800084ac  jz      loc_1800085E0
0x1800084b2  mov     edx, 63h ; 'c'
0x1800084b7  mov     rcx, [rcx+10h]
0x1800084bb  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x1800084c2  mov     r9d, edi
0x1800084c5  call    WPP_SF_d
0x1800084ca  jmp     loc_1800085E0
0x1800084cf  mov     ecx, 30h ; '0'; Size
0x1800084d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800084d9  mov     rbx, rax
0x1800084dc  test    rax, rax
0x1800084df  jz      loc_1800085AB
0x1800084e5  mov     rcx, rax; this
0x1800084e8  call    ??0CManagedObj@@QEAA@XZ; CManagedObj::CManagedObj(void)
0x1800084ed  lea     rax, ??_7CWerComStore@@6BCManagedObj@@@; const CWerComStore::`vftable'{for `CManagedObj'}
0x1800084f4  mov     dword ptr [rbx+28h], 0
0x1800084fb  mov     [rbx], rax
0x1800084fe  lea     rax, ??_7CWerComStore@@6BIWerStore@@@; const CWerComStore::`vftable'{for `IWerStore'}
0x180008505  mov     [rbx+18h], rax
0x180008509  mov     qword ptr [rbx+20h], 0
0x180008511  lock inc dword ptr [rbx+8]
0x180008515  mov     rax, [rsp+28h+arg_0]
0x18000851a  lea     rdx, [rsp+28h+arg_8]
0x18000851f  mov     rcx, rbx
0x180008522  mov     [rsp+28h+arg_8], rax
0x180008527  mov     [rsp+28h+arg_0], 0
0x180008530  call    ?Init@CWerComStore@@QEAAJV?$unique_any@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?WerpCloseStore@@YAX0@Z$0A@@tlx@@@tlx@@@Z; CWerComStore::Init(tlx::unique_any<tlx::handle_traits<void *,void (void *),&WerpCloseStore(void *),0>>)
0x180008535  mov     edi, eax
0x180008537  test    eax, eax
0x180008539  jns     short loc_180008566
0x18000853b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008542  lea     rax, WPP_GLOBAL_Control
0x180008549  cmp     rcx, rax
0x18000854c  jz      loc_1800085E0
0x180008552  test    byte ptr [rcx+1Ch], 1
0x180008556  jz      loc_1800085E0
0x18000855c  mov     edx, 65h ; 'e'
0x180008561  jmp     loc_1800084B7
0x180008566  mov     rax, [rbx]
0x180008569  lea     rdx, IID_IWerStore
0x180008570  mov     r8, rsi
0x180008573  mov     rcx, rbx
0x180008576  mov     rax, [rax]
0x180008579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000857e  mov     edi, eax
0x180008580  test    eax, eax
0x180008582  jns     short loc_1800085A7
0x180008584  mov     rcx, cs:WPP_GLOBAL_Control
0x18000858b  lea     rax, WPP_GLOBAL_Control
0x180008592  cmp     rcx, rax
0x180008595  jz      short loc_1800085E0
0x180008597  test    byte ptr [rcx+1Ch], 1
0x18000859b  jz      short loc_1800085E0
0x18000859d  mov     edx, 66h ; 'f'
0x1800085a2  jmp     loc_1800084B7
0x1800085a7  xor     edi, edi
0x1800085a9  jmp     short loc_1800085E0
0x1800085ab  mov     edi, 8007000Eh
0x1800085b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085b7  lea     rax, WPP_GLOBAL_Control
0x1800085be  cmp     rcx, rax
0x1800085c1  jz      short loc_1800085DE
0x1800085c3  test    byte ptr [rcx+1Ch], 1
0x1800085c7  jz      short loc_1800085DE
0x1800085c9  mov     rcx, [rcx+10h]
0x1800085cd  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x1800085d4  mov     edx, 64h ; 'd'
0x1800085d9  call    WPP_SF_
0x1800085de  xor     ebx, ebx
0x1800085e0  mov     rcx, [rsp+28h+arg_0]
0x1800085e5  mov     [rsp+28h+arg_0], 0
0x1800085ee  test    rcx, rcx
0x1800085f1  jz      short loc_1800085F9
0x1800085f3  call    cs:__imp_WerpCloseStore
0x1800085f9  test    rbx, rbx
0x1800085fc  jz      short loc_18000860D
0x1800085fe  mov     rax, [rbx]
0x180008601  mov     rcx, rbx
0x180008604  mov     rax, [rax+10h]
0x180008608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000860d  mov     rcx, [rsp+28h+arg_0]
0x180008612  test    rcx, rcx
0x180008615  jz      short loc_18000861D
0x180008617  call    cs:__imp_WerpCloseStore
0x18000861d  mov     rbx, [rsp+28h+arg_10]
0x180008622  mov     eax, edi
0x180008624  mov     rsi, [rsp+28h+arg_18]
0x180008629  add     rsp, 20h
0x18000862d  pop     rdi
0x18000862e  retn
```
