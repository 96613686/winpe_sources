# CSREngine::RemoveOldDLDNG1TPBFiles(ushort const *,int,ulong)

- ea: `0x18000f948`
- end: `0x18000fc1b`
- name: `?RemoveOldDLDNG1TPBFiles@CSREngine@@QEAAJPEBGHK@Z`
- size: `723`
- prototype: `__int64 __fastcall(CSREngine *__hidden this, const unsigned __int16 *, int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f948`
- `0x18000fc30`

## callees

- `0x1800061d0`
- `0x18000ca0c`
- `0x18000f948`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSREngine::RemoveOldDLDNG1TPBFiles(
        CSREngine *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4)
{
  char *v7; // rbx
  int v8; // r14d
  int v9; // eax
  int v10; // r13d
  int UserModelFileKeyName; // ebx
  int v12; // eax
  int v13; // r12d
  int v14; // eax
  int v15; // r14d
  int v16; // eax
  int v17; // ebx
  int v19; // [rsp+50h] [rbp-30h]
  LPVOID pv; // [rsp+58h] [rbp-28h] BYREF
  __int64 v21; // [rsp+60h] [rbp-20h] BYREF
  __int64 v22; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+70h] [rbp-10h] BYREF
  int v24; // [rsp+C0h] [rbp+40h]
  unsigned int v25; // [rsp+D8h] [rbp+58h] BYREF

  v25 = a4;
  v23[0] = 0;
  v22 = 0;
  v21 = 0;
  v7 = (char *)this + 16;
  v24 = (**((__int64 (__fastcall ***)(char *, const unsigned __int16 *, __int64, _QWORD, _DWORD, _QWORD *, unsigned int *, _DWORD))this
          + 2))(
          (char *)this + 16,
          a2,
          2,
          a3,
          0,
          v23,
          &v25,
          0);
  v8 = (**(__int64 (__fastcall ***)(char *, const unsigned __int16 *, __int64, _QWORD, _DWORD, __int64 *, unsigned int *, int))v7)(
         v7,
         a2,
         3,
         a3,
         0,
         &v22,
         &v25,
         1);
  v19 = v8;
  v9 = (**(__int64 (__fastcall ***)(char *, const unsigned __int16 *, __int64, _QWORD, _DWORD, __int64 *, unsigned int *, _DWORD))v7)(
         v7,
         a2,
         5,
         a3,
         0,
         &v21,
         &v25,
         0);
  v10 = v9;
  if ( !v24 || !v8 || (UserModelFileKeyName = 0, !v9) )
  {
    if ( v25 <= 1 || (UserModelFileKeyName = CSREngine::RemoveOldDLDNG1TPBFiles(this, a2, a3, v25 - 1)) == 0 )
    {
      pv = 0;
      UserModelFileKeyName = CSREngine::GetUserModelFileKeyName(this, a2, 2, &pv, &v25, 0, 0);
      if ( UserModelFileKeyName >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(_QWORD, char *, LPVOID, __int64))(**((_QWORD **)this + 31) + 160LL))(
                *((_QWORD *)this + 31),
                (char *)this + 112,
                pv,
                1);
        v13 = 0;
        if ( !v24 )
          v13 = v12;
        CoTaskMemFree(pv);
        pv = 0;
        UserModelFileKeyName = CSREngine::GetUserModelFileKeyName(this, a2, 3, &pv, &v25, 0, 1);
        if ( UserModelFileKeyName >= 0 )
        {
          v14 = (*(__int64 (__fastcall **)(_QWORD, char *, LPVOID, __int64))(**((_QWORD **)this + 31) + 160LL))(
                  *((_QWORD *)this + 31),
                  (char *)this + 112,
                  pv,
                  1);
          v15 = 0;
          if ( !v19 )
            v15 = v14;
          CoTaskMemFree(pv);
          pv = 0;
          UserModelFileKeyName = CSREngine::GetUserModelFileKeyName(this, a2, 5, &pv, &v25, 0, 1);
          if ( UserModelFileKeyName >= 0 )
          {
            v16 = (*(__int64 (__fastcall **)(_QWORD, char *, LPVOID, __int64))(**((_QWORD **)this + 31) + 160LL))(
                    *((_QWORD *)this + 31),
                    (char *)this + 112,
                    pv,
                    1);
            v17 = 0;
            if ( !v10 )
              v17 = v16;
            CoTaskMemFree(pv);
            UserModelFileKeyName = v13 < 0 || v15 < 0 || v17 < 0;
          }
        }
      }
    }
  }
  CSpDynamicString::_free((CSpDynamicString *)&v21);
  CSpDynamicString::_free((CSpDynamicString *)&v22);
  CSpDynamicString::_free((CSpDynamicString *)v23);
  return (unsigned int)UserModelFileKeyName;
}

```

## disassembly

```asm
0x18000f948  mov     [rsp-38h+arg_8], rbx
0x18000f94d  mov     [rsp-38h+arg_18], r9d
0x18000f952  push    rbp
0x18000f953  push    rsi
0x18000f954  push    rdi
0x18000f955  push    r12
0x18000f957  push    r13
0x18000f959  push    r14
0x18000f95b  push    r15
0x18000f95d  mov     rbp, rsp
0x18000f960  sub     rsp, 80h
0x18000f967  mov     r15d, r8d
0x18000f96a  mov     rsi, rdx
0x18000f96d  mov     rdi, rcx
0x18000f970  xor     r13d, r13d
0x18000f973  mov     [rbp+var_10], r13
0x18000f977  mov     [rbp+var_18], r13
0x18000f97b  mov     [rbp+var_20], r13
0x18000f97f  lea     rbx, [rcx+10h]
0x18000f983  mov     rax, [rbx]
0x18000f986  mov     [rsp+80h+var_48], r13d
0x18000f98b  lea     rcx, [rbp+arg_18]
0x18000f98f  mov     [rsp+80h+var_50], rcx
0x18000f994  lea     rcx, [rbp+var_10]
0x18000f998  mov     [rsp+80h+var_58], rcx
0x18000f99d  mov     dword ptr [rsp+80h+var_60], r13d
0x18000f9a2  mov     r9d, r8d
0x18000f9a5  lea     r8d, [r13+2]
0x18000f9a9  mov     rcx, rbx
0x18000f9ac  mov     rax, [rax]
0x18000f9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9b4  mov     r12d, eax
0x18000f9b7  mov     [rbp+arg_0], eax
0x18000f9ba  mov     rcx, [rbx]
0x18000f9bd  mov     rax, [rcx]
0x18000f9c0  mov     [rsp+80h+var_48], 1
0x18000f9c8  lea     rcx, [rbp+arg_18]
0x18000f9cc  mov     [rsp+80h+var_50], rcx
0x18000f9d1  lea     rcx, [rbp+var_18]
0x18000f9d5  mov     [rsp+80h+var_58], rcx
0x18000f9da  mov     dword ptr [rsp+80h+var_60], r13d
0x18000f9df  mov     r9d, r15d
0x18000f9e2  lea     r8d, [r13+3]
0x18000f9e6  mov     rdx, rsi
0x18000f9e9  mov     rcx, rbx
0x18000f9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9f1  mov     r14d, eax
0x18000f9f4  mov     [rbp+var_30], eax
0x18000f9f7  mov     rdx, [rbx]
0x18000f9fa  mov     rax, [rdx]
0x18000f9fd  mov     [rsp+80h+var_48], r13d
0x18000fa02  lea     rcx, [rbp+arg_18]
0x18000fa06  mov     [rsp+80h+var_50], rcx
0x18000fa0b  lea     rcx, [rbp+var_20]
0x18000fa0f  mov     [rsp+80h+var_58], rcx
0x18000fa14  mov     dword ptr [rsp+80h+var_60], r13d
0x18000fa19  mov     r9d, r15d
0x18000fa1c  lea     r8d, [r13+5]
0x18000fa20  mov     rdx, rsi
0x18000fa23  mov     rcx, rbx
0x18000fa26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa2b  mov     r13d, eax
0x18000fa2e  test    r12d, r12d
0x18000fa31  jz      short loc_18000FA42
0x18000fa33  test    r14d, r14d
0x18000fa36  jz      short loc_18000FA42
0x18000fa38  xor     ebx, ebx
0x18000fa3a  test    eax, eax
0x18000fa3c  jnz     loc_18000FBE1
0x18000fa42  mov     r9d, [rbp+arg_18]
0x18000fa46  mov     r14d, 1
0x18000fa4c  cmp     r9d, r14d
0x18000fa4f  jbe     short loc_18000FA6C
0x18000fa51  dec     r9d; unsigned int
0x18000fa54  mov     r8d, r15d; int
0x18000fa57  mov     rdx, rsi; unsigned __int16 *
0x18000fa5a  mov     rcx, rdi; this
0x18000fa5d  call    ?RemoveOldDLDNG1TPBFiles@CSREngine@@QEAAJPEBGHK@Z; CSREngine::RemoveOldDLDNG1TPBFiles(ushort const *,int,ulong)
0x18000fa62  mov     ebx, eax
0x18000fa64  test    eax, eax
0x18000fa66  jnz     loc_18000FBE1
0x18000fa6c  mov     [rbp+pv], 0
0x18000fa74  mov     dword ptr [rsp+80h+var_50], 0
0x18000fa7c  mov     [rsp+80h+var_58], 0
0x18000fa85  lea     rax, [rbp+arg_18]
0x18000fa89  mov     [rsp+80h+var_60], rax
0x18000fa8e  lea     r9, [rbp+pv]
0x18000fa92  mov     r8d, 2
0x18000fa98  mov     rdx, rsi
0x18000fa9b  mov     rcx, rdi
0x18000fa9e  call    ?GetUserModelFileKeyName@CSREngine@@QEAAKPEBGW4SR_FILETYPE@@PEAPEAGPEAK3H@Z; CSREngine::GetUserModelFileKeyName(ushort const *,SR_FILETYPE,ushort * *,ulong *,ulong *,int)
0x18000faa3  mov     ebx, eax
0x18000faa5  test    eax, eax
0x18000faa7  js      loc_18000FBE1
0x18000faad  mov     rcx, [rdi+0F8h]
0x18000fab4  lea     r15, [rdi+70h]
0x18000fab8  mov     rax, [rcx]
0x18000fabb  mov     r9d, r14d
0x18000fabe  mov     r8, [rbp+pv]
0x18000fac2  mov     rdx, r15
0x18000fac5  mov     rax, [rax+0A0h]
0x18000facc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fad1  xor     r12d, r12d
0x18000fad4  cmp     [rbp+arg_0], r12d
0x18000fad8  cmovz   r12d, eax
0x18000fadc  mov     rcx, [rbp+pv]; pv
0x18000fae0  call    cs:__imp_CoTaskMemFree
0x18000fae6  mov     [rbp+pv], 0
0x18000faee  mov     dword ptr [rsp+80h+var_50], r14d
0x18000faf3  mov     [rsp+80h+var_58], 0
0x18000fafc  lea     rax, [rbp+arg_18]
0x18000fb00  mov     [rsp+80h+var_60], rax
0x18000fb05  lea     r9, [rbp+pv]
0x18000fb09  mov     r8d, 3
0x18000fb0f  mov     rdx, rsi
0x18000fb12  mov     rcx, rdi
0x18000fb15  call    ?GetUserModelFileKeyName@CSREngine@@QEAAKPEBGW4SR_FILETYPE@@PEAPEAGPEAK3H@Z; CSREngine::GetUserModelFileKeyName(ushort const *,SR_FILETYPE,ushort * *,ulong *,ulong *,int)
0x18000fb1a  mov     ebx, eax
0x18000fb1c  test    eax, eax
0x18000fb1e  js      loc_18000FBE1
0x18000fb24  mov     rcx, [rdi+0F8h]
0x18000fb2b  mov     rax, [rcx]
0x18000fb2e  mov     r9d, r14d
0x18000fb31  mov     r8, [rbp+pv]
0x18000fb35  mov     rdx, r15
0x18000fb38  mov     rax, [rax+0A0h]
0x18000fb3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb44  xor     r14d, r14d
0x18000fb47  cmp     [rbp+var_30], r14d
0x18000fb4b  cmovz   r14d, eax
0x18000fb4f  mov     rcx, [rbp+pv]; pv
0x18000fb53  call    cs:__imp_CoTaskMemFree
0x18000fb59  mov     [rbp+pv], 0
0x18000fb61  mov     dword ptr [rsp+80h+var_50], 1
0x18000fb69  mov     [rsp+80h+var_58], 0
0x18000fb72  lea     rax, [rbp+arg_18]
0x18000fb76  mov     [rsp+80h+var_60], rax
0x18000fb7b  lea     r9, [rbp+pv]
0x18000fb7f  mov     r8d, 5
0x18000fb85  mov     rdx, rsi
0x18000fb88  mov     rcx, rdi
0x18000fb8b  call    ?GetUserModelFileKeyName@CSREngine@@QEAAKPEBGW4SR_FILETYPE@@PEAPEAGPEAK3H@Z; CSREngine::GetUserModelFileKeyName(ushort const *,SR_FILETYPE,ushort * *,ulong *,ulong *,int)
0x18000fb90  mov     ebx, eax
0x18000fb92  test    eax, eax
0x18000fb94  js      short loc_18000FBE1
0x18000fb96  mov     rcx, [rdi+0F8h]
0x18000fb9d  mov     rax, [rcx]
0x18000fba0  mov     edi, 1
0x18000fba5  mov     r9d, edi
0x18000fba8  mov     r8, [rbp+pv]
0x18000fbac  mov     rdx, r15
0x18000fbaf  mov     rax, [rax+0A0h]
0x18000fbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbbb  xor     ebx, ebx
0x18000fbbd  test    r13d, r13d
0x18000fbc0  cmovz   ebx, eax
0x18000fbc3  mov     rcx, [rbp+pv]; pv
0x18000fbc7  call    cs:__imp_CoTaskMemFree
0x18000fbcd  test    r12d, r12d
0x18000fbd0  js      short loc_18000FBDF
0x18000fbd2  test    r14d, r14d
0x18000fbd5  js      short loc_18000FBDF
0x18000fbd7  test    ebx, ebx
0x18000fbd9  js      short loc_18000FBDF
0x18000fbdb  xor     ebx, ebx
0x18000fbdd  jmp     short loc_18000FBE1
0x18000fbdf  mov     ebx, edi
0x18000fbe1  lea     rcx, [rbp+var_20]; this
0x18000fbe5  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x18000fbea  nop
0x18000fbeb  lea     rcx, [rbp+var_18]; this
0x18000fbef  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x18000fbf4  nop
0x18000fbf5  lea     rcx, [rbp+var_10]; this
0x18000fbf9  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x18000fbfe  mov     eax, ebx
0x18000fc00  mov     rbx, [rsp+80h+arg_8]
0x18000fc08  add     rsp, 80h
0x18000fc0f  pop     r15
0x18000fc11  pop     r14
0x18000fc13  pop     r13
0x18000fc15  pop     r12
0x18000fc17  pop     rdi
0x18000fc18  pop     rsi
0x18000fc19  pop     rbp
0x18000fc1a  retn
```
