# ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x1800083ec`
- end: `0x1800084e3`
- name: `?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `247`
- prototype: `__int64 __fastcall(ATL::CComModule *this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a110`

## callees

- `0x180007ae8`
- `0x1800083ec`
- `0x180016010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180008499`
- `KERNEL32!LeaveCriticalSection` at `0x180008499`
- `KERNEL32!EnterCriticalSection` at `0x18000846e`
- `KERNEL32!EnterCriticalSection` at `0x18000846e`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::GetClassObject(
        ATL::CComModule *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v8; // edi
  __int64 v9; // rbx
  ATL::CComModule **v10; // r14

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  v9 = qword_18001DA18;
  if ( qword_18001DA18 )
  {
    while ( *(_QWORD *)v9 )
    {
      if ( *(_QWORD *)(v9 + 16) )
      {
        this = *(ATL::CComModule **)v9;
        if ( a2->Data1 == **(_DWORD **)v9
          && *(_DWORD *)&a2->Data2 == *((_DWORD *)this + 1)
          && *(_DWORD *)a2->Data4 == *((_DWORD *)this + 2)
          && *(_DWORD *)&a2->Data4[4] == *((_DWORD *)this + 3) )
        {
          v10 = (ATL::CComModule **)(v9 + 32);
          if ( !*(_QWORD *)(v9 + 32) )
          {
            EnterCriticalSection(&stru_18001D130);
            if ( !*v10 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v9 + 16))(
                     *(_QWORD *)(v9 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v9 + 32);
            LeaveCriticalSection(&stru_18001D130);
          }
          this = *v10;
          if ( *v10 )
            v8 = (**(__int64 (__fastcall ***)(ATL::CComModule *, const struct _GUID *, void **))this)(this, a3, a4);
          break;
        }
      }
      v9 += 72;
    }
  }
  if ( !*a4 && !v8 )
    return (unsigned int)ATL::AtlComModuleGetClassObject(this, a2, a3, a4);
  return v8;
}

```

## disassembly

```asm
0x1800083ec  push    rbx
0x1800083ee  push    rbp
0x1800083ef  push    rsi
0x1800083f0  push    rdi
0x1800083f1  push    r14
0x1800083f3  push    r15
0x1800083f5  sub     rsp, 28h
0x1800083f9  mov     rsi, r9
0x1800083fc  mov     r15, r8
0x1800083ff  mov     rbp, rdx
0x180008402  test    r9, r9
0x180008405  jnz     short loc_180008411
0x180008407  mov     eax, 80004003h
0x18000840c  jmp     loc_1800084D6
0x180008411  mov     qword ptr [r9], 0
0x180008418  xor     edi, edi
0x18000841a  mov     rbx, cs:qword_18001DA18
0x180008421  test    rbx, rbx
0x180008424  jz      loc_1800084BA
0x18000842a  jmp     short loc_180008457
0x18000842c  cmp     [rbx+10h], rdi
0x180008430  jz      short loc_180008453
0x180008432  mov     rcx, [rbx]
0x180008435  mov     eax, [rcx]
0x180008437  cmp     [rdx], eax
0x180008439  jnz     short loc_180008453
0x18000843b  mov     eax, [rcx+4]
0x18000843e  cmp     [rdx+4], eax
0x180008441  jnz     short loc_180008453
0x180008443  mov     eax, [rcx+8]
0x180008446  cmp     [rdx+8], eax
0x180008449  jnz     short loc_180008453
0x18000844b  mov     eax, [rcx+0Ch]
0x18000844e  cmp     [rdx+0Ch], eax
0x180008451  jz      short loc_18000845E
0x180008453  add     rbx, 48h ; 'H'
0x180008457  cmp     [rbx], rdi
0x18000845a  jnz     short loc_18000842C
0x18000845c  jmp     short loc_1800084BA
0x18000845e  lea     r14, [rbx+20h]
0x180008462  cmp     [r14], rdi
0x180008465  jnz     short loc_18000849F
0x180008467  lea     rcx, stru_18001D130; lpCriticalSection
0x18000846e  call    cs:__imp_EnterCriticalSection
0x180008474  cmp     [r14], rdi
0x180008477  jnz     short loc_180008492
0x180008479  mov     rcx, [rbx+18h]
0x18000847d  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180008484  mov     rax, [rbx+10h]
0x180008488  mov     r8, r14
0x18000848b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008490  mov     edi, eax
0x180008492  lea     rcx, stru_18001D130; lpCriticalSection
0x180008499  call    cs:__imp_LeaveCriticalSection
0x18000849f  mov     rcx, [r14]
0x1800084a2  test    rcx, rcx
0x1800084a5  jz      short loc_1800084BA
0x1800084a7  mov     rax, [rcx]
0x1800084aa  mov     r8, rsi
0x1800084ad  mov     rdx, r15
0x1800084b0  mov     rax, [rax]
0x1800084b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084b8  mov     edi, eax
0x1800084ba  cmp     qword ptr [rsi], 0
0x1800084be  jnz     short loc_1800084D4
0x1800084c0  test    edi, edi
0x1800084c2  jnz     short loc_1800084D4
0x1800084c4  mov     r9, rsi; void **
0x1800084c7  mov     r8, r15; struct _GUID *
0x1800084ca  mov     rdx, rbp; struct _GUID *
0x1800084cd  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800084d2  mov     edi, eax
0x1800084d4  mov     eax, edi
0x1800084d6  add     rsp, 28h
0x1800084da  pop     r15
0x1800084dc  pop     r14
0x1800084de  pop     rdi
0x1800084df  pop     rsi
0x1800084e0  pop     rbp
0x1800084e1  pop     rbx
0x1800084e2  retn
```
