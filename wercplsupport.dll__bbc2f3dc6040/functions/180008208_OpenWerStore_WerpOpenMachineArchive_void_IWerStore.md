# OpenWerStore<&WerpOpenMachineArchive(void * *)>(IWerStore * *)

- ea: `0x180008208`
- end: `0x180008417`
- name: `??$OpenWerStore@$1?WerpOpenMachineArchive@@YAJPEAPEAX@Z@@YAJPEAPEAUIWerStore@@@Z`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000b000`

## callees

- `0x180001634`
- `0x180002850`
- `0x180006c9c`
- `0x1800073d4`
- `0x180008208`
- `0x18000bcfc`
- `0x180013010`

## import_xrefs

- `wer!WerpCloseStore` at `0x1800083db`
- `wer!WerpCloseStore` at `0x1800083ff`
- `wer!WerpCloseStore` at `0x1800083db`
- `wer!WerpCloseStore` at `0x1800083ff`
- `wer!WerpOpenMachineArchive` at `0x18000826d`
- `wer!WerpOpenMachineArchive` at `0x18000826d`

## pseudocode

```c
__int64 __fastcall OpenWerStore<&long WerpOpenMachineArchive(void * *)>(__int64 a1)
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
  v3 = WerpOpenMachineArchive(&v9);
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
0x180008208  mov     [rsp+arg_10], rbx
0x18000820d  mov     [rsp+arg_18], rsi
0x180008212  push    rdi
0x180008213  sub     rsp, 20h
0x180008217  xor     ebx, ebx
0x180008219  mov     [rsp+28h+arg_0], 0
0x180008222  mov     rsi, rcx
0x180008225  test    rcx, rcx
0x180008228  jnz     short loc_180008268
0x18000822a  mov     edi, 80004005h
0x18000822f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008236  lea     rax, WPP_GLOBAL_Control
0x18000823d  cmp     rcx, rax
0x180008240  jz      loc_1800083C8
0x180008246  test    byte ptr [rcx+1Ch], 1
0x18000824a  jz      loc_1800083C8
0x180008250  mov     rcx, [rcx+10h]
0x180008254  lea     edx, [rsi+62h]
0x180008257  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000825e  call    WPP_SF_
0x180008263  jmp     loc_1800083C8
0x180008268  lea     rcx, [rsp+28h+arg_0]
0x18000826d  call    cs:__imp_WerpOpenMachineArchive
0x180008273  mov     edi, eax
0x180008275  test    eax, eax
0x180008277  jns     short loc_1800082B7
0x180008279  mov     rcx, cs:WPP_GLOBAL_Control
0x180008280  lea     rax, WPP_GLOBAL_Control
0x180008287  cmp     rcx, rax
0x18000828a  jz      loc_1800083C8
0x180008290  test    byte ptr [rcx+1Ch], 1
0x180008294  jz      loc_1800083C8
0x18000829a  mov     edx, 63h ; 'c'
0x18000829f  mov     rcx, [rcx+10h]
0x1800082a3  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x1800082aa  mov     r9d, edi
0x1800082ad  call    WPP_SF_d
0x1800082b2  jmp     loc_1800083C8
0x1800082b7  mov     ecx, 30h ; '0'; Size
0x1800082bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800082c1  mov     rbx, rax
0x1800082c4  test    rax, rax
0x1800082c7  jz      loc_180008393
0x1800082cd  mov     rcx, rax; this
0x1800082d0  call    ??0CManagedObj@@QEAA@XZ; CManagedObj::CManagedObj(void)
0x1800082d5  lea     rax, ??_7CWerComStore@@6BCManagedObj@@@; const CWerComStore::`vftable'{for `CManagedObj'}
0x1800082dc  mov     dword ptr [rbx+28h], 0
0x1800082e3  mov     [rbx], rax
0x1800082e6  lea     rax, ??_7CWerComStore@@6BIWerStore@@@; const CWerComStore::`vftable'{for `IWerStore'}
0x1800082ed  mov     [rbx+18h], rax
0x1800082f1  mov     qword ptr [rbx+20h], 0
0x1800082f9  lock inc dword ptr [rbx+8]
0x1800082fd  mov     rax, [rsp+28h+arg_0]
0x180008302  lea     rdx, [rsp+28h+arg_8]
0x180008307  mov     rcx, rbx
0x18000830a  mov     [rsp+28h+arg_8], rax
0x18000830f  mov     [rsp+28h+arg_0], 0
0x180008318  call    ?Init@CWerComStore@@QEAAJV?$unique_any@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?WerpCloseStore@@YAX0@Z$0A@@tlx@@@tlx@@@Z; CWerComStore::Init(tlx::unique_any<tlx::handle_traits<void *,void (void *),&WerpCloseStore(void *),0>>)
0x18000831d  mov     edi, eax
0x18000831f  test    eax, eax
0x180008321  jns     short loc_18000834E
0x180008323  mov     rcx, cs:WPP_GLOBAL_Control
0x18000832a  lea     rax, WPP_GLOBAL_Control
0x180008331  cmp     rcx, rax
0x180008334  jz      loc_1800083C8
0x18000833a  test    byte ptr [rcx+1Ch], 1
0x18000833e  jz      loc_1800083C8
0x180008344  mov     edx, 65h ; 'e'
0x180008349  jmp     loc_18000829F
0x18000834e  mov     rax, [rbx]
0x180008351  lea     rdx, IID_IWerStore
0x180008358  mov     r8, rsi
0x18000835b  mov     rcx, rbx
0x18000835e  mov     rax, [rax]
0x180008361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008366  mov     edi, eax
0x180008368  test    eax, eax
0x18000836a  jns     short loc_18000838F
0x18000836c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008373  lea     rax, WPP_GLOBAL_Control
0x18000837a  cmp     rcx, rax
0x18000837d  jz      short loc_1800083C8
0x18000837f  test    byte ptr [rcx+1Ch], 1
0x180008383  jz      short loc_1800083C8
0x180008385  mov     edx, 66h ; 'f'
0x18000838a  jmp     loc_18000829F
0x18000838f  xor     edi, edi
0x180008391  jmp     short loc_1800083C8
0x180008393  mov     edi, 8007000Eh
0x180008398  mov     rcx, cs:WPP_GLOBAL_Control
0x18000839f  lea     rax, WPP_GLOBAL_Control
0x1800083a6  cmp     rcx, rax
0x1800083a9  jz      short loc_1800083C6
0x1800083ab  test    byte ptr [rcx+1Ch], 1
0x1800083af  jz      short loc_1800083C6
0x1800083b1  mov     rcx, [rcx+10h]
0x1800083b5  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x1800083bc  mov     edx, 64h ; 'd'
0x1800083c1  call    WPP_SF_
0x1800083c6  xor     ebx, ebx
0x1800083c8  mov     rcx, [rsp+28h+arg_0]
0x1800083cd  mov     [rsp+28h+arg_0], 0
0x1800083d6  test    rcx, rcx
0x1800083d9  jz      short loc_1800083E1
0x1800083db  call    cs:__imp_WerpCloseStore
0x1800083e1  test    rbx, rbx
0x1800083e4  jz      short loc_1800083F5
0x1800083e6  mov     rax, [rbx]
0x1800083e9  mov     rcx, rbx
0x1800083ec  mov     rax, [rax+10h]
0x1800083f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083f5  mov     rcx, [rsp+28h+arg_0]
0x1800083fa  test    rcx, rcx
0x1800083fd  jz      short loc_180008405
0x1800083ff  call    cs:__imp_WerpCloseStore
0x180008405  mov     rbx, [rsp+28h+arg_10]
0x18000840a  mov     eax, edi
0x18000840c  mov     rsi, [rsp+28h+arg_18]
0x180008411  add     rsp, 20h
0x180008415  pop     rdi
0x180008416  retn
```
