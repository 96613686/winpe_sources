# W3WP_HOST::GetPreloadProvider(ushort const *,ushort const *,STRU *)

- ea: `0x180004798`
- end: `0x1800049c6`
- name: `?GetPreloadProvider@W3WP_HOST@@QEAAJPEBG0PEAVSTRU@@@Z`
- size: `558`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct STRU *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180004100`

## callees

- `0x180004798`
- `0x18000e010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004921`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004921`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180004939`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180004939`

## string_xrefs

- `0x1800047f4`: `system.applicationHost/serviceAutoStartProviders`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::GetPreloadProvider(
        W3WP_HOST *this,
        const unsigned __int16 *a2,
        char *a3,
        struct STRU *a4)
{
  __int64 v4; // rcx
  int v7; // ebx
  unsigned int v8; // eax
  unsigned int i; // esi
  unsigned __int16 *v10; // rax
  int v11; // r8d
  int v12; // edx
  __int64 v13; // rax
  __int64 *v15; // [rsp+40h] [rbp-30h] BYREF
  __int64 v16; // [rsp+48h] [rbp-28h] BYREF
  __int64 v17; // [rsp+50h] [rbp-20h] BYREF
  __int64 v18; // [rsp+58h] [rbp-18h] BYREF
  char *v19; // [rsp+60h] [rbp-10h] BYREF
  const unsigned __int16 *v20; // [rsp+68h] [rbp-8h] BYREF
  unsigned int v21; // [rsp+A0h] [rbp+30h] BYREF

  v4 = *((_QWORD *)this + 24);
  v18 = 0;
  v17 = 0;
  v16 = 0;
  v15 = 0;
  v21 = 0;
  v19 = 0;
  v20 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v4 + 24LL))(
         v4,
         L"system.applicationHost/serviceAutoStartProviders",
         a2,
         &v18,
         &v17,
         0);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 40LL))(v18, &v16);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v16 + 24LL))(v16, &v21);
      if ( v7 >= 0 )
      {
        v8 = v21;
        if ( v21 )
        {
          for ( i = 0; i < v8; ++i )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v16 + 32LL))(v16, i, &v15);
            if ( v7 < 0 )
              goto LABEL_20;
            v7 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, char **, _QWORD, _QWORD))(*v15 + 64))(
                   v15,
                   L"name",
                   &v19,
                   0,
                   0);
            if ( v7 < 0 )
              goto LABEL_20;
            v10 = (unsigned __int16 *)v19;
            do
            {
              v11 = *(unsigned __int16 *)((char *)v10 + a3 - v19);
              v12 = *v10 - v11;
              if ( v12 )
                break;
              ++v10;
            }
            while ( v11 );
            v13 = *v15;
            if ( !v12 )
            {
              v7 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(v13 + 64))(
                     v15,
                     L"type",
                     &v20,
                     0,
                     0);
              if ( v7 < 0 )
                goto LABEL_20;
              v7 = STRU::Copy(a4, v20);
              if ( v7 < 0 )
                goto LABEL_20;
              v7 = 0;
              break;
            }
            (*(void (**)(void))(v13 + 16))();
            v8 = v21;
            v15 = 0;
          }
          if ( STRU::IsEmpty(a4) )
            v7 = 1;
        }
        else
        {
          v7 = 1;
        }
      }
    }
  }
LABEL_20:
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
    v15 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004798  mov     r11, rsp
0x18000479b  mov     [r11+10h], rbx
0x18000479f  mov     [r11+18h], rsi
0x1800047a3  push    rbp
0x1800047a4  push    rdi
0x1800047a5  push    r12
0x1800047a7  push    r14
0x1800047a9  push    r15
0x1800047ab  mov     rbp, rsp
0x1800047ae  sub     rsp, 70h
0x1800047b2  mov     rcx, [rcx+0C0h]
0x1800047b9  xor     r12d, r12d
0x1800047bc  mov     r15, r8
0x1800047bf  mov     [rbp+var_18], r12
0x1800047c3  mov     [rbp+var_20], r12
0x1800047c7  lea     r8, [rbp+var_20]
0x1800047cb  mov     [rbp+var_28], r12
0x1800047cf  mov     r14, r9
0x1800047d2  mov     [rbp+var_30], r12
0x1800047d6  lea     r9, [rbp+var_18]
0x1800047da  mov     [rbp+arg_0], r12d
0x1800047de  mov     [rbp+var_10], r12
0x1800047e2  mov     [rbp+var_8], r12
0x1800047e6  mov     rax, [rcx]
0x1800047e9  mov     [r11-70h], r12
0x1800047ed  mov     [r11-78h], r8
0x1800047f1  mov     r8, rdx
0x1800047f4  lea     rdx, aSystemApplicat_0; "system.applicationHost/serviceAutoStart"...
0x1800047fb  mov     rax, [rax+18h]
0x1800047ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004804  mov     ebx, eax
0x180004806  test    eax, eax
0x180004808  js      loc_18000494A
0x18000480e  mov     rcx, [rbp+var_18]
0x180004812  lea     rdx, [rbp+var_28]
0x180004816  mov     rax, [rcx]
0x180004819  mov     rax, [rax+28h]
0x18000481d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004822  mov     ebx, eax
0x180004824  test    eax, eax
0x180004826  js      loc_18000494A
0x18000482c  mov     rcx, [rbp+var_28]
0x180004830  lea     rdx, [rbp+arg_0]
0x180004834  mov     rax, [rcx]
0x180004837  mov     rax, [rax+18h]
0x18000483b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004840  mov     ebx, eax
0x180004842  test    eax, eax
0x180004844  js      loc_18000494A
0x18000484a  mov     eax, [rbp+arg_0]
0x18000484d  test    eax, eax
0x18000484f  jnz     short loc_180004859
0x180004851  lea     ebx, [rax+1]
0x180004854  jmp     loc_18000494A
0x180004859  mov     esi, r12d
0x18000485c  mov     edi, 1
0x180004861  cmp     esi, eax
0x180004863  jnb     loc_180004936
0x180004869  mov     rcx, [rbp+var_28]
0x18000486d  lea     r8, [rbp+var_30]
0x180004871  mov     edx, esi
0x180004873  mov     rax, [rcx]
0x180004876  mov     rax, [rax+20h]
0x18000487a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000487f  mov     ebx, eax
0x180004881  test    eax, eax
0x180004883  js      loc_18000494A
0x180004889  mov     rcx, [rbp+var_30]
0x18000488d  lea     r8, [rbp+var_10]
0x180004891  xor     r9d, r9d
0x180004894  mov     [rsp+70h+var_50], r12
0x180004899  lea     rdx, aName; "name"
0x1800048a0  mov     rax, [rcx]
0x1800048a3  mov     rax, [rax+40h]
0x1800048a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048ac  mov     ebx, eax
0x1800048ae  test    eax, eax
0x1800048b0  js      loc_18000494A
0x1800048b6  mov     rax, [rbp+var_10]
0x1800048ba  mov     rcx, r15
0x1800048bd  sub     rcx, rax
0x1800048c0  movzx   edx, word ptr [rax]
0x1800048c3  movzx   r8d, word ptr [rax+rcx]
0x1800048c8  sub     edx, r8d
0x1800048cb  jnz     short loc_1800048D6
0x1800048cd  add     rax, 2
0x1800048d1  test    r8d, r8d
0x1800048d4  jnz     short loc_1800048C0
0x1800048d6  mov     rcx, [rbp+var_30]
0x1800048da  mov     rax, [rcx]
0x1800048dd  test    edx, edx
0x1800048df  jz      short loc_1800048F8
0x1800048e1  mov     rax, [rax+10h]
0x1800048e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048ea  mov     eax, [rbp+arg_0]
0x1800048ed  add     esi, edi
0x1800048ef  mov     [rbp+var_30], r12
0x1800048f3  jmp     loc_180004861
0x1800048f8  mov     rax, [rax+40h]
0x1800048fc  lea     r8, [rbp+var_8]
0x180004900  xor     r9d, r9d
0x180004903  mov     [rsp+70h+var_50], r12
0x180004908  lea     rdx, aType; "type"
0x18000490f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004914  mov     ebx, eax
0x180004916  test    eax, eax
0x180004918  js      short loc_18000494A
0x18000491a  mov     rdx, [rbp+var_8]
0x18000491e  mov     rcx, r14
0x180004921  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004928  nop     dword ptr [rax+rax+00h]
0x18000492d  mov     ebx, eax
0x18000492f  test    eax, eax
0x180004931  js      short loc_18000494A
0x180004933  mov     ebx, r12d
0x180004936  mov     rcx, r14
0x180004939  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180004940  nop     dword ptr [rax+rax+00h]
0x180004945  test    al, al
0x180004947  cmovnz  ebx, edi
0x18000494a  mov     rcx, [rbp+var_30]
0x18000494e  test    rcx, rcx
0x180004951  jz      short loc_180004963
0x180004953  mov     rax, [rcx]
0x180004956  mov     rax, [rax+10h]
0x18000495a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000495f  mov     [rbp+var_30], r12
0x180004963  mov     rcx, [rbp+var_28]
0x180004967  test    rcx, rcx
0x18000496a  jz      short loc_18000497C
0x18000496c  mov     rax, [rcx]
0x18000496f  mov     rax, [rax+10h]
0x180004973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004978  mov     [rbp+var_28], r12
0x18000497c  mov     rcx, [rbp+var_20]
0x180004980  test    rcx, rcx
0x180004983  jz      short loc_180004995
0x180004985  mov     rax, [rcx]
0x180004988  mov     rax, [rax+10h]
0x18000498c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004991  mov     [rbp+var_20], r12
0x180004995  mov     rcx, [rbp+var_18]
0x180004999  test    rcx, rcx
0x18000499c  jz      short loc_1800049AA
0x18000499e  mov     rax, [rcx]
0x1800049a1  mov     rax, [rax+10h]
0x1800049a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049aa  lea     r11, [rsp+70h+var_s0]
0x1800049af  mov     eax, ebx
0x1800049b1  mov     rbx, [r11+38h]
0x1800049b5  mov     rsi, [r11+40h]
0x1800049b9  mov     rsp, r11
0x1800049bc  pop     r15
0x1800049be  pop     r14
0x1800049c0  pop     r12
0x1800049c2  pop     rdi
0x1800049c3  pop     rbp
0x1800049c4  retn
```
