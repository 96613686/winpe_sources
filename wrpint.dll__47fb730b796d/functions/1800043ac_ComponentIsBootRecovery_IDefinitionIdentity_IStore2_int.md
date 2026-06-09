# ComponentIsBootRecovery(IDefinitionIdentity *,IStore2 *,int *)

- ea: `0x1800043ac`
- end: `0x180004583`
- name: `?ComponentIsBootRecovery@@YAJPEAUIDefinitionIdentity@@PEAUIStore2@@PEAH@Z`
- size: `471`
- prototype: `__int64 __fastcall(struct IDefinitionIdentity *, struct IStore2 *, int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002d00`
- `0x1800031c0`
- `0x180003a40`
- `0x180003df0`

## callees

- `0x1800043ac`
- `0x18001b7b0`
- `0x18001c010`

## string_xrefs

- `0x18000443b`: `BootRecovery,Microsoft.Windows.Categories,publicKeyToken=365143bb27e7ac8b,version=1.0.0.0`

## pseudocode

```c
__int64 __fastcall ComponentIsBootRecovery(struct IDefinitionIdentity *a1, struct IStore2 *a2, int *a3)
{
  int v5; // ebx
  int (*v6)(struct IIdentityAuthority **); // rax
  __int64 v8; // [rsp+40h] [rbp-40h] BYREF
  __int64 v9; // [rsp+48h] [rbp-38h] BYREF
  __int64 v10; // [rsp+50h] [rbp-30h] BYREF
  struct IDefinitionIdentity *v11; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v12; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v13; // [rsp+64h] [rbp-1Ch] BYREF
  int v14; // [rsp+68h] [rbp-18h] BYREF

  v11 = a1;
  v9 = 0;
  v8 = 0;
  v10 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  if ( !a3 )
    return (unsigned int)-2147024809;
  v6 = vpfnGetIdentityAuthority;
  *a3 = 0;
  v5 = ((__int64 (__fastcall *)(__int64 *))v6)(&v9);
  if ( v5 < 0 )
    goto LABEL_14;
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, __int64 *))(*(_QWORD *)v9 + 24LL))(
         v9,
         0,
         L"BootRecovery,Microsoft.Windows.Categories,publicKeyToken=365143bb27e7ac8b,version=1.0.0.0",
         &v10);
  if ( v5 < 0 )
    goto LABEL_14;
  (*(void (__fastcall **)(struct IStore2 *, __int64, __int64, struct IDefinitionIdentity **, GUID *, __int64 *))(*(_QWORD *)a2 + 248LL))(
    a2,
    1,
    1,
    &v11,
    &GUID_e19364f9_e580_4867_936c_f2d4fb7a49dc,
    &v8);
  if ( v8 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v8 + 24LL))(v8, &v12);
    if ( v5 >= 0 && v12 != -1 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, unsigned int *))(*(_QWORD *)v8 + 144LL))(
             v8,
             0,
             v12,
             2,
             &v13);
      if ( v5 >= 0 && v13 != -1 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, int *))(*(_QWORD *)v8 + 160LL))(
               v8,
               0,
               v13,
               v10,
               &v14);
        if ( v5 >= 0 && v14 != -1 )
          *a3 = 1;
      }
    }
LABEL_14:
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    goto LABEL_16;
  }
  v5 = 0;
LABEL_16:
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800043ac  mov     [rsp-18h+arg_18], rbx
0x1800043b1  push    rbp
0x1800043b2  push    rsi
0x1800043b3  push    rdi
0x1800043b4  mov     rbp, rsp
0x1800043b7  sub     rsp, 80h
0x1800043be  mov     rax, cs:__security_cookie
0x1800043c5  xor     rax, rsp
0x1800043c8  mov     [rbp+var_10], rax
0x1800043cc  mov     [rbp+var_28], rcx
0x1800043d0  mov     rdi, r8
0x1800043d3  mov     [rbp+var_38], 0
0x1800043db  mov     rsi, rdx
0x1800043de  mov     [rbp+var_40], 0
0x1800043e6  mov     [rbp+var_30], 0
0x1800043ee  mov     [rbp+var_20], 0
0x1800043f5  mov     [rbp+var_1C], 0
0x1800043fc  mov     [rbp+var_18], 0
0x180004403  test    r8, r8
0x180004406  jnz     short loc_180004412
0x180004408  mov     ebx, 80070057h
0x18000440d  jmp     loc_180004562
0x180004412  mov     rax, cs:?vpfnGetIdentityAuthority@@3P6AJPEAPEAUIIdentityAuthority@@@ZEA; long (*vpfnGetIdentityAuthority)(IIdentityAuthority * *)
0x180004419  lea     rcx, [rbp+var_38]
0x18000441d  mov     dword ptr [r8], 0
0x180004424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004429  mov     ebx, eax
0x18000442b  test    eax, eax
0x18000442d  js      loc_180004523
0x180004433  mov     rcx, [rbp+var_38]
0x180004437  lea     r9, [rbp+var_30]
0x18000443b  lea     r8, aBootrecoveryMi; "BootRecovery,Microsoft.Windows.Categori"...
0x180004442  xor     edx, edx
0x180004444  mov     rax, [rcx]
0x180004447  mov     rax, [rax+18h]
0x18000444b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004450  mov     ebx, eax
0x180004452  test    eax, eax
0x180004454  js      loc_180004523
0x18000445a  mov     rax, [rsi]
0x18000445d  lea     rcx, [rbp+var_40]
0x180004461  mov     [rsp+80h+var_58], rcx
0x180004466  lea     r9, [rbp+var_28]
0x18000446a  lea     rcx, _GUID_e19364f9_e580_4867_936c_f2d4fb7a49dc
0x180004471  mov     edx, 1
0x180004476  mov     [rsp+80h+var_60], rcx
0x18000447b  mov     r8d, edx
0x18000447e  mov     rax, [rax+0F8h]
0x180004485  mov     rcx, rsi
0x180004488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000448d  mov     rcx, [rbp+var_40]
0x180004491  test    rcx, rcx
0x180004494  jnz     short loc_18000449D
0x180004496  xor     ebx, ebx
0x180004498  jmp     loc_180004538
0x18000449d  mov     rax, [rcx]
0x1800044a0  lea     rdx, [rbp+var_20]
0x1800044a4  mov     rax, [rax+18h]
0x1800044a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ad  mov     ebx, eax
0x1800044af  test    eax, eax
0x1800044b1  js      short loc_180004523
0x1800044b3  mov     r8d, [rbp+var_20]
0x1800044b7  or      esi, 0FFFFFFFFh
0x1800044ba  cmp     r8d, esi
0x1800044bd  jz      short loc_180004523
0x1800044bf  mov     rcx, [rbp+var_40]
0x1800044c3  lea     rdx, [rbp+var_1C]
0x1800044c7  mov     [rsp+80h+var_60], rdx
0x1800044cc  xor     edx, edx
0x1800044ce  mov     rax, [rcx]
0x1800044d1  lea     r9d, [rdx+2]
0x1800044d5  mov     rax, [rax+90h]
0x1800044dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044e1  mov     ebx, eax
0x1800044e3  test    eax, eax
0x1800044e5  js      short loc_180004523
0x1800044e7  mov     r8d, [rbp+var_1C]
0x1800044eb  cmp     r8d, esi
0x1800044ee  jz      short loc_180004523
0x1800044f0  mov     rcx, [rbp+var_40]
0x1800044f4  lea     rdx, [rbp+var_18]
0x1800044f8  mov     r9, [rbp+var_30]
0x1800044fc  mov     [rsp+80h+var_60], rdx
0x180004501  xor     edx, edx
0x180004503  mov     rax, [rcx]
0x180004506  mov     rax, [rax+0A0h]
0x18000450d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004512  mov     ebx, eax
0x180004514  test    eax, eax
0x180004516  js      short loc_180004523
0x180004518  cmp     [rbp+var_18], esi
0x18000451b  jz      short loc_180004523
0x18000451d  mov     dword ptr [rdi], 1
0x180004523  mov     rcx, [rbp+var_40]
0x180004527  test    rcx, rcx
0x18000452a  jz      short loc_180004538
0x18000452c  mov     rax, [rcx]
0x18000452f  mov     rax, [rax+10h]
0x180004533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004538  mov     rcx, [rbp+var_38]
0x18000453c  test    rcx, rcx
0x18000453f  jz      short loc_18000454D
0x180004541  mov     rax, [rcx]
0x180004544  mov     rax, [rax+10h]
0x180004548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000454d  mov     rcx, [rbp+var_30]
0x180004551  test    rcx, rcx
0x180004554  jz      short loc_180004562
0x180004556  mov     rax, [rcx]
0x180004559  mov     rax, [rax+10h]
0x18000455d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004562  mov     eax, ebx
0x180004564  mov     rcx, [rbp+var_10]
0x180004568  xor     rcx, rsp; StackCookie
0x18000456b  call    __security_check_cookie
0x180004570  mov     rbx, [rsp+80h+arg_18]
0x180004578  add     rsp, 80h
0x18000457f  pop     rdi
0x180004580  pop     rsi
0x180004581  pop     rbp
0x180004582  retn
```
