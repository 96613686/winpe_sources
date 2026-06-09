# W3WP_HOST::GetPreloadProvider(ushort const *,ushort const *,STRU *)

- ea: `0x1800043d8`
- end: `0x1800045f9`
- name: `?GetPreloadProvider@W3WP_HOST@@QEAAJPEBG0PEAVSTRU@@@Z`
- size: `545`
- prototype: `__int64 __fastcall(W3WP_HOST *this, const unsigned __int16 *, char *, struct STRU *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180003df0`

## callees

- `0x1800043d8`
- `0x18000d010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004561`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004561`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180004573`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180004573`

## string_xrefs

- `0x180004434`: `system.applicationHost/serviceAutoStartProviders`

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
0x1800043d8  mov     r11, rsp
0x1800043db  mov     [r11+10h], rbx
0x1800043df  mov     [r11+18h], rsi
0x1800043e3  push    rbp
0x1800043e4  push    rdi
0x1800043e5  push    r12
0x1800043e7  push    r14
0x1800043e9  push    r15
0x1800043eb  mov     rbp, rsp
0x1800043ee  sub     rsp, 70h
0x1800043f2  mov     rcx, [rcx+0C0h]
0x1800043f9  xor     r12d, r12d
0x1800043fc  mov     r15, r8
0x1800043ff  mov     [rbp+var_18], r12
0x180004403  mov     [rbp+var_20], r12
0x180004407  lea     r8, [rbp+var_20]
0x18000440b  mov     [rbp+var_28], r12
0x18000440f  mov     r14, r9
0x180004412  mov     [rbp+var_30], r12
0x180004416  lea     r9, [rbp+var_18]
0x18000441a  mov     [rbp+arg_0], r12d
0x18000441e  mov     [rbp+var_10], r12
0x180004422  mov     [rbp+var_8], r12
0x180004426  mov     rax, [rcx]
0x180004429  mov     [r11-70h], r12
0x18000442d  mov     [r11-78h], r8
0x180004431  mov     r8, rdx
0x180004434  lea     rdx, aSystemApplicat_0; "system.applicationHost/serviceAutoStart"...
0x18000443b  mov     rax, [rax+18h]
0x18000443f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004444  mov     ebx, eax
0x180004446  test    eax, eax
0x180004448  js      loc_18000457E
0x18000444e  mov     rcx, [rbp+var_18]
0x180004452  lea     rdx, [rbp+var_28]
0x180004456  mov     rax, [rcx]
0x180004459  mov     rax, [rax+28h]
0x18000445d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004462  mov     ebx, eax
0x180004464  test    eax, eax
0x180004466  js      loc_18000457E
0x18000446c  mov     rcx, [rbp+var_28]
0x180004470  lea     rdx, [rbp+arg_0]
0x180004474  mov     rax, [rcx]
0x180004477  mov     rax, [rax+18h]
0x18000447b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004480  mov     ebx, eax
0x180004482  test    eax, eax
0x180004484  js      loc_18000457E
0x18000448a  mov     eax, [rbp+arg_0]
0x18000448d  test    eax, eax
0x18000448f  jnz     short loc_180004499
0x180004491  lea     ebx, [rax+1]
0x180004494  jmp     loc_18000457E
0x180004499  mov     esi, r12d
0x18000449c  mov     edi, 1
0x1800044a1  cmp     esi, eax
0x1800044a3  jnb     loc_180004570
0x1800044a9  mov     rcx, [rbp+var_28]
0x1800044ad  lea     r8, [rbp+var_30]
0x1800044b1  mov     edx, esi
0x1800044b3  mov     rax, [rcx]
0x1800044b6  mov     rax, [rax+20h]
0x1800044ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044bf  mov     ebx, eax
0x1800044c1  test    eax, eax
0x1800044c3  js      loc_18000457E
0x1800044c9  mov     rcx, [rbp+var_30]
0x1800044cd  lea     r8, [rbp+var_10]
0x1800044d1  xor     r9d, r9d
0x1800044d4  mov     [rsp+70h+var_50], r12
0x1800044d9  lea     rdx, aName; "name"
0x1800044e0  mov     rax, [rcx]
0x1800044e3  mov     rax, [rax+40h]
0x1800044e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ec  mov     ebx, eax
0x1800044ee  test    eax, eax
0x1800044f0  js      loc_18000457E
0x1800044f6  mov     rax, [rbp+var_10]
0x1800044fa  mov     rcx, r15
0x1800044fd  sub     rcx, rax
0x180004500  movzx   edx, word ptr [rax]
0x180004503  movzx   r8d, word ptr [rax+rcx]
0x180004508  sub     edx, r8d
0x18000450b  jnz     short loc_180004516
0x18000450d  add     rax, 2
0x180004511  test    r8d, r8d
0x180004514  jnz     short loc_180004500
0x180004516  mov     rcx, [rbp+var_30]
0x18000451a  mov     rax, [rcx]
0x18000451d  test    edx, edx
0x18000451f  jz      short loc_180004538
0x180004521  mov     rax, [rax+10h]
0x180004525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000452a  mov     eax, [rbp+arg_0]
0x18000452d  add     esi, edi
0x18000452f  mov     [rbp+var_30], r12
0x180004533  jmp     loc_1800044A1
0x180004538  mov     rax, [rax+40h]
0x18000453c  lea     r8, [rbp+var_8]
0x180004540  xor     r9d, r9d
0x180004543  mov     [rsp+70h+var_50], r12
0x180004548  lea     rdx, aType; "type"
0x18000454f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004554  mov     ebx, eax
0x180004556  test    eax, eax
0x180004558  js      short loc_18000457E
0x18000455a  mov     rdx, [rbp+var_8]
0x18000455e  mov     rcx, r14
0x180004561  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004567  mov     ebx, eax
0x180004569  test    eax, eax
0x18000456b  js      short loc_18000457E
0x18000456d  mov     ebx, r12d
0x180004570  mov     rcx, r14
0x180004573  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180004579  test    al, al
0x18000457b  cmovnz  ebx, edi
0x18000457e  mov     rcx, [rbp+var_30]
0x180004582  test    rcx, rcx
0x180004585  jz      short loc_180004597
0x180004587  mov     rax, [rcx]
0x18000458a  mov     rax, [rax+10h]
0x18000458e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004593  mov     [rbp+var_30], r12
0x180004597  mov     rcx, [rbp+var_28]
0x18000459b  test    rcx, rcx
0x18000459e  jz      short loc_1800045B0
0x1800045a0  mov     rax, [rcx]
0x1800045a3  mov     rax, [rax+10h]
0x1800045a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ac  mov     [rbp+var_28], r12
0x1800045b0  mov     rcx, [rbp+var_20]
0x1800045b4  test    rcx, rcx
0x1800045b7  jz      short loc_1800045C9
0x1800045b9  mov     rax, [rcx]
0x1800045bc  mov     rax, [rax+10h]
0x1800045c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045c5  mov     [rbp+var_20], r12
0x1800045c9  mov     rcx, [rbp+var_18]
0x1800045cd  test    rcx, rcx
0x1800045d0  jz      short loc_1800045DE
0x1800045d2  mov     rax, [rcx]
0x1800045d5  mov     rax, [rax+10h]
0x1800045d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045de  lea     r11, [rsp+70h+var_s0]
0x1800045e3  mov     eax, ebx
0x1800045e5  mov     rbx, [r11+38h]
0x1800045e9  mov     rsi, [r11+40h]
0x1800045ed  mov     rsp, r11
0x1800045f0  pop     r15
0x1800045f2  pop     r14
0x1800045f4  pop     r12
0x1800045f6  pop     rdi
0x1800045f7  pop     rbp
0x1800045f8  retn
```
