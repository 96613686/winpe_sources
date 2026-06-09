# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180003728`
- end: `0x18000382e`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005ba0`

## callees

- `0x180003728`
- `0x18001d010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800037c5`
- `KERNEL32!EnterCriticalSection` at `0x1800037c5`
- `KERNEL32!LeaveCriticalSection` at `0x1800037f0`
- `KERNEL32!LeaveCriticalSection` at `0x1800037f0`

## pseudocode

```c
__int64 __fastcall ATL::AtlComModuleGetClassObject(
        struct ATL::_ATL_COM_MODULE70 *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v8; // ebx
  __int64 *i; // rcx
  __int64 v10; // rsi
  _DWORD *v11; // rdx
  _QWORD *v12; // rdi

  if ( !ATL::_AtlComModule )
    return 2147549183LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  for ( i = off_18002E100[0]; i < off_18002E108; ++i )
  {
    v10 = *i;
    if ( *i )
    {
      if ( *(_QWORD *)(v10 + 16) )
      {
        v11 = *(_DWORD **)v10;
        if ( a2->Data1 == **(_DWORD **)v10
          && *(_DWORD *)&a2->Data2 == v11[1]
          && *(_DWORD *)a2->Data4 == v11[2]
          && *(_DWORD *)&a2->Data4[4] == v11[3] )
        {
          v12 = (_QWORD *)(v10 + 32);
          if ( !*(_QWORD *)(v10 + 32) )
          {
            EnterCriticalSection(&CriticalSection);
            if ( !*v12 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                     *(_QWORD *)(v10 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v10 + 32);
            LeaveCriticalSection(&CriticalSection);
          }
          if ( *v12 )
            v8 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v12)(*v12, a3, a4);
          break;
        }
      }
    }
  }
  if ( !*a4 && !v8 )
    return (unsigned int)-2147221231;
  return v8;
}

```

## disassembly

```asm
0x180003728  push    rbx
0x18000372a  push    rbp
0x18000372b  push    rsi
0x18000372c  push    rdi
0x18000372d  push    r14
0x18000372f  sub     rsp, 20h
0x180003733  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000373a  mov     r14, r9
0x18000373d  mov     r9, rdx
0x180003740  mov     rbp, r8
0x180003743  jnz     short loc_18000374F
0x180003745  mov     eax, 8000FFFFh
0x18000374a  jmp     loc_180003823
0x18000374f  test    r14, r14
0x180003752  jnz     short loc_18000375E
0x180003754  mov     eax, 80004003h
0x180003759  jmp     loc_180003823
0x18000375e  mov     qword ptr [r14], 0
0x180003765  xor     ebx, ebx
0x180003767  mov     rcx, cs:off_18002E100
0x18000376e  mov     r8, cs:off_18002E108
0x180003775  jmp     short loc_1800037AE
0x180003777  mov     rsi, [rcx]
0x18000377a  test    rsi, rsi
0x18000377d  jz      short loc_1800037AA
0x18000377f  cmp     [rsi+10h], rbx
0x180003783  jz      short loc_1800037AA
0x180003785  mov     rdx, [rsi]
0x180003788  mov     eax, [rdx]
0x18000378a  cmp     [r9], eax
0x18000378d  jnz     short loc_1800037AA
0x18000378f  mov     eax, [rdx+4]
0x180003792  cmp     [r9+4], eax
0x180003796  jnz     short loc_1800037AA
0x180003798  mov     eax, [rdx+8]
0x18000379b  cmp     [r9+8], eax
0x18000379f  jnz     short loc_1800037AA
0x1800037a1  mov     eax, [rdx+0Ch]
0x1800037a4  cmp     [r9+0Ch], eax
0x1800037a8  jz      short loc_1800037B5
0x1800037aa  add     rcx, 8
0x1800037ae  cmp     rcx, r8
0x1800037b1  jb      short loc_180003777
0x1800037b3  jmp     short loc_180003811
0x1800037b5  lea     rdi, [rsi+20h]
0x1800037b9  cmp     [rdi], rbx
0x1800037bc  jnz     short loc_1800037F6
0x1800037be  lea     rcx, CriticalSection; lpCriticalSection
0x1800037c5  call    cs:__imp_EnterCriticalSection
0x1800037cb  cmp     [rdi], rbx
0x1800037ce  jnz     short loc_1800037E9
0x1800037d0  mov     rcx, [rsi+18h]
0x1800037d4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800037db  mov     rax, [rsi+10h]
0x1800037df  mov     r8, rdi
0x1800037e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e7  mov     ebx, eax
0x1800037e9  lea     rcx, CriticalSection; lpCriticalSection
0x1800037f0  call    cs:__imp_LeaveCriticalSection
0x1800037f6  mov     rcx, [rdi]
0x1800037f9  test    rcx, rcx
0x1800037fc  jz      short loc_180003811
0x1800037fe  mov     rax, [rcx]
0x180003801  mov     r8, r14
0x180003804  mov     rdx, rbp
0x180003807  mov     rax, [rax]
0x18000380a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000380f  mov     ebx, eax
0x180003811  cmp     qword ptr [r14], 0
0x180003815  jnz     short loc_180003821
0x180003817  test    ebx, ebx
0x180003819  mov     eax, 80040111h
0x18000381e  cmovz   ebx, eax
0x180003821  mov     eax, ebx
0x180003823  add     rsp, 20h
0x180003827  pop     r14
0x180003829  pop     rdi
0x18000382a  pop     rsi
0x18000382b  pop     rbp
0x18000382c  pop     rbx
0x18000382d  retn
```
