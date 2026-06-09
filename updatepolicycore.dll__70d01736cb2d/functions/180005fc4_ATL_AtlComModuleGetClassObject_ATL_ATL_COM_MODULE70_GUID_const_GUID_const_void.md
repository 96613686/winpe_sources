# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180005fc4`
- end: `0x18000611c`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `344`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004960`

## callees

- `0x180005fc4`
- `0x18002ffd0`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000607a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000607a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800060be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800060be`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800060cc`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800060cc`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800060ae`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800060ae`

## pseudocode

```c
__int64 __fastcall ATL::AtlComModuleGetClassObject(
        struct ATL::_ATL_COM_MODULE70 *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  GUID ***v8; // rcx
  int v9; // ebx
  GUID **v10; // rsi
  GUID *v11; // rdx
  PVOID *v12; // rdi
  GUID *v13; // rcx
  GUID *v14; // rax
  __int64 (__fastcall ***v15)(PVOID, const struct _GUID *, void **); // rax
  PVOID Ptr; // [rsp+20h] [rbp-28h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !ATL::_AtlComModule )
    return 2147549183LL;
  v8 = off_18004B4B0;
  v9 = 0;
  while ( 1 )
  {
    if ( v8 >= (GUID ***)off_18004B4B8 )
      return (unsigned int)-2147221231;
    v10 = *v8;
    if ( *v8 )
    {
      if ( v10[2] )
      {
        v11 = *v10;
        if ( a2->Data1 == (*v10)->Data1
          && *(_DWORD *)&a2->Data2 == *(_DWORD *)&v11->Data2
          && *(_DWORD *)a2->Data4 == *(_DWORD *)v11->Data4
          && *(_DWORD *)&a2->Data4[4] == *(_DWORD *)&v11->Data4[4] )
        {
          break;
        }
      }
    }
    ++v8;
  }
  v12 = (PVOID *)v10[4];
  if ( !*v12 )
  {
    EnterCriticalSection(&stru_18004B4C0);
    if ( !*v12 )
    {
      v13 = v10[3];
      v14 = v10[2];
      Ptr = 0;
      v9 = ((__int64 (__fastcall *)(GUID *, GUID *, PVOID *))v14)(v13, &GUID_00000000_0000_0000_c000_000000000046, &Ptr);
      if ( v9 >= 0 )
        *v12 = EncodePointer(Ptr);
    }
    LeaveCriticalSection(&stru_18004B4C0);
  }
  if ( *v12 )
  {
    v15 = (__int64 (__fastcall ***)(PVOID, const struct _GUID *, void **))DecodePointer(*v12);
    v9 = (**v15)(v15, a3, a4);
  }
  if ( !*a4 && !v9 )
    return (unsigned int)-2147221231;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180005fc4  mov     [rsp+arg_0], rbx
0x180005fc9  mov     [rsp+arg_8], rbp
0x180005fce  push    rsi
0x180005fcf  push    rdi
0x180005fd0  push    r14
0x180005fd2  sub     rsp, 30h
0x180005fd6  mov     rax, cs:__security_cookie
0x180005fdd  xor     rax, rsp
0x180005fe0  mov     [rsp+48h+var_20], rax
0x180005fe5  mov     rbp, r8
0x180005fe8  mov     r8, rdx
0x180005feb  mov     r14, r9
0x180005fee  test    r9, r9
0x180005ff1  jnz     short loc_180005FFD
0x180005ff3  mov     eax, 80004003h
0x180005ff8  jmp     loc_1800060FC
0x180005ffd  mov     qword ptr [r9], 0
0x180006004  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000600b  jnz     short loc_180006017
0x18000600d  mov     eax, 8000FFFFh
0x180006012  jmp     loc_1800060FC
0x180006017  mov     rcx, cs:off_18004B4B0
0x18000601e  xor     ebx, ebx
0x180006020  mov     r9, cs:off_18004B4B8
0x180006027  jmp     short loc_180006060
0x180006029  mov     rsi, [rcx]
0x18000602c  test    rsi, rsi
0x18000602f  jz      short loc_18000605C
0x180006031  cmp     [rsi+10h], rbx
0x180006035  jz      short loc_18000605C
0x180006037  mov     rdx, [rsi]
0x18000603a  mov     eax, [rdx]
0x18000603c  cmp     [r8], eax
0x18000603f  jnz     short loc_18000605C
0x180006041  mov     eax, [rdx+4]
0x180006044  cmp     [r8+4], eax
0x180006048  jnz     short loc_18000605C
0x18000604a  mov     eax, [rdx+8]
0x18000604d  cmp     [r8+8], eax
0x180006051  jnz     short loc_18000605C
0x180006053  mov     eax, [rdx+0Ch]
0x180006056  cmp     [r8+0Ch], eax
0x18000605a  jz      short loc_18000606A
0x18000605c  add     rcx, 8
0x180006060  cmp     rcx, r9
0x180006063  jb      short loc_180006029
0x180006065  jmp     loc_1800060F5
0x18000606a  mov     rdi, [rsi+20h]
0x18000606e  cmp     [rdi], rbx
0x180006071  jnz     short loc_1800060C4
0x180006073  lea     rcx, stru_18004B4C0; lpCriticalSection
0x18000607a  call    cs:__imp_EnterCriticalSection
0x180006080  cmp     [rdi], rbx
0x180006083  jnz     short loc_1800060B7
0x180006085  mov     rcx, [rsi+18h]
0x180006089  lea     r8, [rsp+48h+Ptr]
0x18000608e  mov     rax, [rsi+10h]
0x180006092  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180006099  mov     [rsp+48h+Ptr], rbx
0x18000609e  call    _guard_dispatch_icall
0x1800060a3  mov     ebx, eax
0x1800060a5  test    eax, eax
0x1800060a7  js      short loc_1800060B7
0x1800060a9  mov     rcx, [rsp+48h+Ptr]; Ptr
0x1800060ae  call    cs:__imp_EncodePointer
0x1800060b4  mov     [rdi], rax
0x1800060b7  lea     rcx, stru_18004B4C0; lpCriticalSection
0x1800060be  call    cs:__imp_LeaveCriticalSection
0x1800060c4  mov     rcx, [rdi]; Ptr
0x1800060c7  test    rcx, rcx
0x1800060ca  jz      short loc_1800060EB
0x1800060cc  call    cs:__imp_DecodePointer
0x1800060d2  mov     r8, r14
0x1800060d5  mov     rdx, rbp
0x1800060d8  mov     r9, rax
0x1800060db  mov     rcx, [rax]
0x1800060de  mov     rax, [rcx]
0x1800060e1  mov     rcx, r9
0x1800060e4  call    _guard_dispatch_icall
0x1800060e9  mov     ebx, eax
0x1800060eb  cmp     qword ptr [r14], 0
0x1800060ef  jnz     short loc_1800060FA
0x1800060f1  test    ebx, ebx
0x1800060f3  jnz     short loc_1800060FA
0x1800060f5  mov     ebx, 80040111h
0x1800060fa  mov     eax, ebx
0x1800060fc  mov     rcx, [rsp+48h+var_20]
0x180006101  xor     rcx, rsp; StackCookie
0x180006104  call    __security_check_cookie
0x180006109  mov     rbx, [rsp+48h+arg_0]
0x18000610e  mov     rbp, [rsp+48h+arg_8]
0x180006113  add     rsp, 30h
0x180006117  pop     r14
0x180006119  pop     rdi
0x18000611a  pop     rsi
0x18000611b  retn
```
