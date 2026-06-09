# CStorage::MakePathConsistent(ushort const *,CDynamicArray<ushort,ushort *> &,int)

- ea: `0x1800165ac`
- end: `0x18001668c`
- name: `?MakePathConsistent@CStorage@@SAHPEBGAEAV?$CDynamicArray@GPEAG@@H@Z`
- size: `224`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800120e0`
- `0x1800174c0`

## callees

- `0x180009e30`
- `0x1800165ac`
- `0x180017f94`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcslwr` at `0x180016676`
- `msvcrt!_wcslwr` at `0x180016676`

## pseudocode

```c
__int64 __fastcall CStorage::MakePathConsistent(size_t *a1, _QWORD *a2, int a3)
{
  __int64 v5; // rdx
  unsigned int v7; // eax

  if ( a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *((_WORD *)a1 + v5) );
    if ( !(unsigned int)CDynamicArray<unsigned short,unsigned short *>::SetSize(a2, v5 + 1)
      || (int)StringCchCopyW((unsigned __int16 *)*a2, a2[1], a1) < 0 )
    {
      return 0;
    }
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(struct IKernel32Interface *, size_t *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)g_Kernel32
                                                                                                  + 320LL))(
           g_Kernel32,
           a1,
           0,
           0,
           0);
    if ( !v7
      || !(unsigned int)CDynamicArray<unsigned short,unsigned short *>::SetSize(a2, v7)
      || (*(unsigned int (__fastcall **)(struct IKernel32Interface *, size_t *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)g_Kernel32 + 320LL))(
           g_Kernel32,
           a1,
           *((unsigned int *)a2 + 2),
           *a2,
           0) != a2[1] - 1LL )
    {
      return 0;
    }
  }
  _wcslwr((wchar_t *)*a2);
  return 1;
}

```

## disassembly

```asm
0x1800165ac  mov     [rsp+arg_0], rbx
0x1800165b1  mov     [rsp+arg_8], rsi
0x1800165b6  push    rdi
0x1800165b7  sub     rsp, 30h
0x1800165bb  xor     esi, esi
0x1800165bd  mov     rbx, rdx
0x1800165c0  mov     rdi, rcx
0x1800165c3  test    r8d, r8d
0x1800165c6  jz      short loc_18001660A
0x1800165c8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800165cc  inc     rdx
0x1800165cf  cmp     [rcx+rdx*2], si
0x1800165d3  jnz     short loc_1800165CC
0x1800165d5  inc     rdx
0x1800165d8  mov     rcx, rbx
0x1800165db  call    ?SetSize@?$CDynamicArray@GPEAG@@QEAAH_K@Z; CDynamicArray<ushort,ushort *>::SetSize(unsigned __int64)
0x1800165e0  test    eax, eax
0x1800165e2  jz      short loc_1800165F7
0x1800165e4  mov     rdx, [rbx+8]; unsigned __int64
0x1800165e8  mov     r8, rdi; unsigned __int16 *
0x1800165eb  mov     rcx, [rbx]; unsigned __int16 *
0x1800165ee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800165f3  test    eax, eax
0x1800165f5  jns     short loc_180016673
0x1800165f7  xor     eax, eax
0x1800165f9  mov     rbx, [rsp+38h+arg_0]
0x1800165fe  mov     rsi, [rsp+38h+arg_8]
0x180016603  add     rsp, 30h
0x180016607  pop     rdi
0x180016608  retn
0x18001660a  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180016611  xor     r9d, r9d
0x180016614  xor     r8d, r8d
0x180016617  mov     [rsp+38h+var_18], rsi
0x18001661c  mov     rdx, rdi
0x18001661f  mov     rax, [rcx]
0x180016622  mov     rax, [rax+140h]
0x180016629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001662e  mov     edx, eax
0x180016630  test    eax, eax
0x180016632  jz      short loc_1800165F7
0x180016634  mov     rcx, rbx
0x180016637  call    ?SetSize@?$CDynamicArray@GPEAG@@QEAAH_K@Z; CDynamicArray<ushort,ushort *>::SetSize(unsigned __int64)
0x18001663c  test    eax, eax
0x18001663e  jz      short loc_1800165F7
0x180016640  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180016647  mov     rdx, rdi
0x18001664a  mov     r9, [rbx]
0x18001664d  mov     r8d, [rbx+8]
0x180016651  mov     [rsp+38h+var_18], rsi
0x180016656  mov     rax, [rcx]
0x180016659  mov     rax, [rax+140h]
0x180016660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016665  mov     rcx, [rbx+8]
0x180016669  dec     rcx
0x18001666c  mov     edx, eax
0x18001666e  cmp     rdx, rcx
0x180016671  jnz     short loc_1800165F7
0x180016673  mov     rcx, [rbx]; String
0x180016676  call    cs:__imp__wcslwr
0x18001667d  nop     dword ptr [rax+rax+00h]
0x180016682  mov     eax, 1
0x180016687  jmp     loc_1800165F9
```
