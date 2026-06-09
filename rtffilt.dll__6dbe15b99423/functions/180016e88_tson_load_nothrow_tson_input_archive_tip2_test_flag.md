# tson::load_nothrow(tson::input_archive &,tip2::test_flag &)

- ea: `0x180016e88`
- end: `0x180017408`
- name: `?load_nothrow@tson@@YAXAEAVinput_archive@1@AEAUtest_flag@tip2@@@Z`
- size: `1408`
- prototype: `void __fastcall(tson *__hidden this, struct tson::input_archive *, struct tip2::test_flag *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e748`

## callees

- `0x18000dc28`
- `0x18000ec38`
- `0x18000eff8`
- `0x18000f4e0`
- `0x180016d60`
- `0x180016e88`
- `0x180018644`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017291`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017291`

## pseudocode

```c
void __fastcall tson::load_nothrow(tson *this, struct tson::input_archive *a2, struct tip2::test_flag *a3)
{
  unsigned __int16 *v3; // rbx
  __int64 v6; // r8
  __int64 v7; // r8
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  __int64 v13; // rcx
  _BYTE *v14; // rdx
  __int64 v15; // rdx
  char *v16; // rax
  char v17; // cl
  __int16 v18; // ax
  __int64 v19; // rcx
  _BYTE *v20; // rdx
  bool v21; // zf
  __int64 v22; // rcx
  _QWORD *v23; // rdx
  __int64 v24; // rcx
  _BYTE *v25; // rdx
  bool v26; // zf
  _DWORD *v27; // rdx
  __int64 v28; // rcx
  _BYTE *v29; // rdx
  _WORD *v30; // rdx
  __int64 v31; // rcx
  _BYTE *v32; // rdx
  char *v33; // rax
  char v34; // cl
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  const char *v40; // rax
  const char *v41; // rbx
  void *v42; // rax
  _BYTE *v43; // rdx
  _BYTE *v44; // rdx
  _BYTE *v45; // rdx
  _QWORD v46[2]; // [rsp+20h] [rbp-60h] BYREF
  const char *v47; // [rsp+30h] [rbp-50h] BYREF
  __int64 v48; // [rsp+38h] [rbp-48h]
  struct tson::input_archive *v49; // [rsp+40h] [rbp-40h]
  const char *v50; // [rsp+48h] [rbp-38h] BYREF
  char v51; // [rsp+50h] [rbp-30h]
  _QWORD *v52; // [rsp+58h] [rbp-28h]
  const char *v53; // [rsp+60h] [rbp-20h] BYREF
  char v54; // [rsp+68h] [rbp-18h]
  void **v55; // [rsp+70h] [rbp-10h]
  void *v56; // [rsp+A8h] [rbp+28h] BYREF

  v49 = a2;
  *((_QWORD *)a2 + 1) = (char *)a2 + 40;
  v3 = (unsigned __int16 *)((char *)a2 + 16);
  v46[0] = (char *)a2 + 40;
  v46[1] = 64;
  v53 = "type";
  v54 = 4;
  v50 = "name";
  v55 = (void **)((char *)a2 + 16);
  v52 = v46;
  v47 = "reason";
  v51 = 4;
  LOBYTE(v48) = 6;
  tson::input_archive::process<tson::nvp<unsigned short &>>(this, &v47, a3);
  tson::input_archive::process<tson::nvp<tson::ansistring_buffer_tag &>>(this, &v50);
  tson::input_archive::process<tson::nvp<unsigned short &>>(this, &v53, v6);
  v8 = *v3;
  if ( v8 > 0x11 )
  {
    v35 = v8 - 18;
    if ( !v35 )
    {
      v54 = 5;
      v53 = "value";
      v55 = (void **)((char *)a2 + 24);
      tson::input_archive::process<tson::nvp<unsigned short &>>(this, &v53, v7);
      return;
    }
    v36 = v35 - 1;
    if ( !v36 )
    {
      *((_BYTE *)this + 24) = 5;
      *((_QWORD *)this + 2) = "value";
      if ( tson::input_archive::search(this) )
      {
        v24 = *(_QWORD *)this;
        v45 = *(_BYTE **)(*(_QWORD *)this + 8LL);
        if ( (unsigned __int64)v45 < *(_QWORD *)(*(_QWORD *)this + 16LL) )
        {
          *(_QWORD *)(v24 + 8) = v45 + 1;
          if ( !v45 )
            goto LABEL_42;
          v26 = *v45 == 18;
LABEL_38:
          if ( !v26 && *((int *)this + 2) >= 0 )
            *((_DWORD *)this + 2) = -2147023267;
LABEL_42:
          v22 = *(_QWORD *)this;
          v27 = *(_DWORD **)(*(_QWORD *)this + 8LL);
          if ( (unsigned __int64)(v27 + 1) <= *(_QWORD *)(*(_QWORD *)this + 16LL) )
          {
            *((_DWORD *)a2 + 6) = *v27;
            *(_QWORD *)(v22 + 8) += 4LL;
            return;
          }
          goto LABEL_33;
        }
LABEL_41:
        *(_BYTE *)(v24 + 24) = 1;
        goto LABEL_42;
      }
LABEL_44:
      *((_DWORD *)a2 + 6) = 0;
      return;
    }
    v37 = v36 - 1;
    if ( !v37 )
    {
      *((_BYTE *)this + 24) = 5;
      *((_QWORD *)this + 2) = "value";
      if ( tson::input_archive::search(this) )
      {
        v19 = *(_QWORD *)this;
        v44 = *(_BYTE **)(*(_QWORD *)this + 8LL);
        if ( (unsigned __int64)v44 < *(_QWORD *)(*(_QWORD *)this + 16LL) )
        {
          *(_QWORD *)(v19 + 8) = v44 + 1;
          if ( !v44 )
            goto LABEL_31;
          v21 = *v44 == 19;
LABEL_27:
          if ( !v21 && *((int *)this + 2) >= 0 )
            *((_DWORD *)this + 2) = -2147023267;
LABEL_31:
          v22 = *(_QWORD *)this;
          v23 = *(_QWORD **)(*(_QWORD *)this + 8LL);
          if ( (unsigned __int64)(v23 + 1) <= *(_QWORD *)(*(_QWORD *)this + 16LL) )
          {
            *((_QWORD *)a2 + 3) = *v23;
            *(_QWORD *)(v22 + 8) += 8LL;
            return;
          }
          goto LABEL_33;
        }
LABEL_30:
        *(_BYTE *)(v19 + 24) = 1;
        goto LABEL_31;
      }
      goto LABEL_90;
    }
    v38 = v37 - 1;
    if ( !v38 )
    {
      *((_BYTE *)this + 24) = 5;
      *((_QWORD *)this + 2) = "value";
      if ( tson::input_archive::search(this) )
      {
        v19 = *(_QWORD *)this;
        v43 = *(_BYTE **)(*(_QWORD *)this + 8LL);
        if ( (unsigned __int64)v43 < *(_QWORD *)(*(_QWORD *)this + 16LL) )
        {
          *(_QWORD *)(v19 + 8) = v43 + 1;
          if ( !v43 )
            goto LABEL_31;
          v21 = *v43 == 20;
          goto LABEL_27;
        }
        goto LABEL_30;
      }
LABEL_90:
      v42 = 0;
      goto LABEL_91;
    }
    v39 = v38 - 9;
    if ( !v39 )
    {
      v56 = 0;
      *((_QWORD *)this + 2) = "value";
      *((_BYTE *)this + 24) = 5;
      tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(
        this,
        &v56);
      v42 = v56;
LABEL_91:
      *((_QWORD *)a2 + 3) = v42;
      return;
    }
    if ( v39 != 1 )
      goto LABEL_72;
    *((_BYTE *)this + 24) = 5;
    *((_QWORD *)this + 2) = "value";
    v47 = 0;
    v49 = 0;
    v48 = 0;
    tson::input_archive::loadValue(this, (struct tson::string_tag *)&v47);
    if ( v48 )
    {
      v40 = (const char *)CoTaskMemAlloc(2 * v48);
      v41 = v40;
      if ( v40 )
      {
        v47 = v40;
        tson::input_archive::loadValue(this, (struct tson::string_tag *)&v47);
LABEL_80:
        *((_QWORD *)a2 + 3) = v41;
        return;
      }
      if ( *((int *)this + 2) >= 0 )
        *((_DWORD *)this + 2) = -2147024882;
    }
    v41 = 0;
    goto LABEL_80;
  }
  if ( v8 != 17 )
  {
    if ( !*v3 )
      return;
    v9 = v8 - 2;
    if ( !v9 )
    {
      *((_BYTE *)this + 24) = 5;
      *((_QWORD *)this + 2) = "value";
      if ( !tson::input_archive::search(this) )
      {
        v18 = 0;
        goto LABEL_55;
      }
      v28 = *(_QWORD *)this;
      v29 = *(_BYTE **)(*(_QWORD *)this + 8LL);
      if ( (unsigned __int64)v29 >= *(_QWORD *)(*(_QWORD *)this + 16LL) )
      {
        *(_BYTE *)(v28 + 24) = 1;
      }
      else
      {
        *(_QWORD *)(v28 + 8) = v29 + 1;
        if ( v29 && *v29 != 13 && *((int *)this + 2) >= 0 )
          *((_DWORD *)this + 2) = -2147023267;
      }
      v22 = *(_QWORD *)this;
      v30 = *(_WORD **)(*(_QWORD *)this + 8LL);
      if ( (unsigned __int64)(v30 + 1) <= *(_QWORD *)(*(_QWORD *)this + 16LL) )
      {
        *((_WORD *)a2 + 12) = *v30;
        *(_QWORD *)(v22 + 8) += 2LL;
        return;
      }
LABEL_33:
      *(_BYTE *)(v22 + 24) = 1;
      return;
    }
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 2;
      if ( v11 )
      {
        v12 = v11 - 6;
        if ( v12 )
        {
          if ( v12 == 5 )
          {
            *((_BYTE *)this + 24) = 5;
            *((_QWORD *)this + 2) = "value";
            if ( tson::input_archive::search(this) )
            {
              v13 = *(_QWORD *)this;
              v14 = *(_BYTE **)(*(_QWORD *)this + 8LL);
              if ( (unsigned __int64)v14 >= *(_QWORD *)(*(_QWORD *)this + 16LL) )
              {
                *(_BYTE *)(v13 + 24) = 1;
              }
              else
              {
                *(_QWORD *)(v13 + 8) = v14 + 1;
                if ( v14 && *v14 != 11 && *((int *)this + 2) >= 0 )
                  *((_DWORD *)this + 2) = -2147023267;
              }
              v15 = *(_QWORD *)this;
              v16 = *(char **)(*(_QWORD *)this + 8LL);
              if ( (unsigned __int64)v16 < *(_QWORD *)(*(_QWORD *)this + 16LL) )
              {
                v17 = *v16;
                *(_QWORD *)(v15 + 8) = v16 + 1;
                *((_BYTE *)v3 + 8) = v17;
                return;
              }
              goto LABEL_18;
            }
            *((_BYTE *)v3 + 8) = 0;
            return;
          }
LABEL_72:
          if ( *((int *)this + 2) >= 0 )
            *((_DWORD *)this + 2) = -2147024119;
          return;
        }
        LOBYTE(v56) = 0;
        v53 = "value";
        v54 = 5;
        v55 = &v56;
        tson::input_archive::process<tson::nvp<bool &>>(this, &v53);
        if ( (_BYTE)v56 )
          v18 = -1;
        else
          v18 = 0;
LABEL_55:
        *((_WORD *)a2 + 12) = v18;
        return;
      }
      *((_BYTE *)this + 24) = 5;
      *((_QWORD *)this + 2) = "value";
      if ( tson::input_archive::search(this) )
      {
        v19 = *(_QWORD *)this;
        v20 = *(_BYTE **)(*(_QWORD *)this + 8LL);
        if ( (unsigned __int64)v20 < *(_QWORD *)(*(_QWORD *)this + 16LL) )
        {
          *(_QWORD *)(v19 + 8) = v20 + 1;
          if ( !v20 )
            goto LABEL_31;
          v21 = *v20 == 21;
          goto LABEL_27;
        }
        goto LABEL_30;
      }
      goto LABEL_90;
    }
    *((_BYTE *)this + 24) = 5;
    *((_QWORD *)this + 2) = "value";
    if ( tson::input_archive::search(this) )
    {
      v24 = *(_QWORD *)this;
      v25 = *(_BYTE **)(*(_QWORD *)this + 8LL);
      if ( (unsigned __int64)v25 < *(_QWORD *)(*(_QWORD *)this + 16LL) )
      {
        *(_QWORD *)(v24 + 8) = v25 + 1;
        if ( !v25 )
          goto LABEL_42;
        v26 = *v25 == 17;
        goto LABEL_38;
      }
      goto LABEL_41;
    }
    goto LABEL_44;
  }
  *((_BYTE *)this + 24) = 5;
  *((_QWORD *)this + 2) = "value";
  if ( tson::input_archive::search(this) )
  {
    v31 = *(_QWORD *)this;
    v32 = *(_BYTE **)(*(_QWORD *)this + 8LL);
    if ( (unsigned __int64)v32 >= *(_QWORD *)(*(_QWORD *)this + 16LL) )
    {
      *(_BYTE *)(v31 + 24) = 1;
    }
    else
    {
      *(_QWORD *)(v31 + 8) = v32 + 1;
      if ( v32 && *v32 != 12 && *((int *)this + 2) >= 0 )
        *((_DWORD *)this + 2) = -2147023267;
    }
    v15 = *(_QWORD *)this;
    v33 = *(char **)(*(_QWORD *)this + 8LL);
    if ( (unsigned __int64)v33 >= *(_QWORD *)(*(_QWORD *)this + 16LL) )
    {
LABEL_18:
      *(_BYTE *)(v15 + 24) = 1;
      return;
    }
    v34 = *v33;
    *(_QWORD *)(v15 + 8) = v33 + 1;
    *((_BYTE *)a2 + 24) = v34;
  }
  else
  {
    *((_BYTE *)a2 + 24) = 0;
  }
}

```

## disassembly

```asm
0x180016e88  mov     [rsp-18h+arg_0], rbx
0x180016e8d  mov     [rsp-18h+arg_10], rsi
0x180016e92  push    rbp
0x180016e93  push    rdi
0x180016e94  push    r14
0x180016e96  mov     rbp, rsp
0x180016e99  sub     rsp, 80h
0x180016ea0  lea     rax, [rdx+28h]
0x180016ea4  mov     [rbp+var_40], rdx
0x180016ea8  mov     [rdx+8], rax
0x180016eac  lea     rbx, [rdx+10h]
0x180016eb0  mov     [rbp+var_60], rax
0x180016eb4  mov     rsi, rdx
0x180016eb7  lea     rax, aType; "type"
0x180016ebe  mov     [rbp+var_58], 40h ; '@'
0x180016ec6  mov     [rbp+var_20], rax
0x180016eca  lea     rdx, [rbp+var_50]
0x180016ece  lea     rax, aName; "name"
0x180016ed5  mov     [rbp+var_18], 4
0x180016ed9  mov     [rbp+var_38], rax
0x180016edd  mov     rdi, rcx
0x180016ee0  lea     rax, [rbp+var_60]
0x180016ee4  mov     [rbp+var_10], rbx
0x180016ee8  mov     [rbp+var_28], rax
0x180016eec  lea     rax, aReason; "reason"
0x180016ef3  mov     [rbp+var_50], rax
0x180016ef7  mov     [rbp+var_30], 4
0x180016efb  mov     byte ptr [rbp+var_48], 6
0x180016eff  call    ??$process@V?$nvp@AEAG@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAG@1@@Z; tson::input_archive::process<tson::nvp<ushort &>>(tson::nvp<ushort &> &&)
0x180016f04  lea     rdx, [rbp+var_38]
0x180016f08  mov     rcx, rdi
0x180016f0b  call    ??$process@V?$nvp@AEAUansistring_buffer_tag@tson@@@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAUansistring_buffer_tag@tson@@@1@@Z; tson::input_archive::process<tson::nvp<tson::ansistring_buffer_tag &>>(tson::nvp<tson::ansistring_buffer_tag &> &&)
0x180016f10  lea     rdx, [rbp+var_20]
0x180016f14  mov     rcx, rdi
0x180016f17  call    ??$process@V?$nvp@AEAG@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAG@1@@Z; tson::input_archive::process<tson::nvp<ushort &>>(tson::nvp<ushort &> &&)
0x180016f1c  movzx   ecx, word ptr [rbx]
0x180016f1f  xor     r14d, r14d
0x180016f22  cmp     ecx, 11h
0x180016f25  ja      loc_18001720A
0x180016f2b  jz      loc_180017191
0x180016f31  test    ecx, ecx
0x180016f33  jz      loc_1800173F0
0x180016f39  sub     ecx, 2
0x180016f3c  jz      loc_180017113
0x180016f42  sub     ecx, 1
0x180016f45  jz      loc_18001709C
0x180016f4b  sub     ecx, 2
0x180016f4e  jz      loc_180017020
0x180016f54  sub     ecx, 6
0x180016f57  jz      loc_180016FE3
0x180016f5d  cmp     ecx, 5
0x180016f60  jnz     loc_18001723C
0x180016f66  lea     rax, aValue; "value"
0x180016f6d  mov     [rdi+18h], cl
0x180016f70  mov     rcx, rdi; this
0x180016f73  mov     [rdi+10h], rax
0x180016f77  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x180016f7c  test    al, al
0x180016f7e  jz      short loc_180016FD9
0x180016f80  mov     rcx, [rdi]
0x180016f83  mov     rdx, [rcx+8]
0x180016f87  cmp     rdx, [rcx+10h]
0x180016f8b  jnb     short loc_180016FAE
0x180016f8d  lea     rax, [rdx+1]
0x180016f91  mov     [rcx+8], rax
0x180016f95  test    rdx, rdx
0x180016f98  jz      short loc_180016FB2
0x180016f9a  cmp     byte ptr [rdx], 0Bh
0x180016f9d  jz      short loc_180016FB2
0x180016f9f  cmp     [rdi+8], r14d
0x180016fa3  jl      short loc_180016FB2
0x180016fa5  mov     dword ptr [rdi+8], 8007065Dh
0x180016fac  jmp     short loc_180016FB2
0x180016fae  mov     byte ptr [rcx+18h], 1
0x180016fb2  mov     rdx, [rdi]
0x180016fb5  mov     rax, [rdx+8]
0x180016fb9  cmp     rax, [rdx+10h]
0x180016fbd  jnb     short loc_180016FD0
0x180016fbf  mov     cl, [rax]
0x180016fc1  inc     rax
0x180016fc4  mov     [rdx+8], rax
0x180016fc8  mov     [rbx+8], cl
0x180016fcb  jmp     loc_1800173F0
0x180016fd0  mov     byte ptr [rdx+18h], 1
0x180016fd4  jmp     loc_1800173F0
0x180016fd9  xor     eax, eax
0x180016fdb  mov     [rbx+8], al
0x180016fde  jmp     loc_1800173F0
0x180016fe3  lea     rax, aValue; "value"
0x180016fea  mov     byte ptr [rbp+arg_8], r14b
0x180016fee  mov     [rbp+var_20], rax
0x180016ff2  lea     rdx, [rbp+var_20]
0x180016ff6  lea     rax, [rbp+arg_8]
0x180016ffa  mov     [rbp+var_18], 5
0x180016ffe  mov     rcx, rdi
0x180017001  mov     [rbp+var_10], rax
0x180017005  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18001700a  cmp     byte ptr [rbp+arg_8], r14b
0x18001700e  jz      short loc_180017018
0x180017010  or      eax, 0FFFFFFFFh
0x180017013  jmp     loc_180017188
0x180017018  mov     eax, r14d
0x18001701b  jmp     loc_180017188
0x180017020  lea     rax, aValue; "value"
0x180017027  mov     byte ptr [rdi+18h], 5
0x18001702b  mov     rcx, rdi; this
0x18001702e  mov     [rdi+10h], rax
0x180017032  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x180017037  test    al, al
0x180017039  jz      loc_18001737C
0x18001703f  mov     rcx, [rdi]
0x180017042  mov     rdx, [rcx+8]
0x180017046  cmp     rdx, [rcx+10h]
0x18001704a  jnb     short loc_18001706D
0x18001704c  lea     rax, [rdx+1]
0x180017050  mov     [rcx+8], rax
0x180017054  test    rdx, rdx
0x180017057  jz      short loc_180017071
0x180017059  cmp     byte ptr [rdx], 15h
0x18001705c  jz      short loc_180017071
0x18001705e  cmp     [rdi+8], r14d
0x180017062  jl      short loc_180017071
0x180017064  mov     dword ptr [rdi+8], 8007065Dh
0x18001706b  jmp     short loc_180017071
0x18001706d  mov     byte ptr [rcx+18h], 1
0x180017071  mov     rcx, [rdi]
0x180017074  mov     rdx, [rcx+8]
0x180017078  lea     rax, [rdx+8]
0x18001707c  cmp     rax, [rcx+10h]
0x180017080  ja      short loc_180017093
0x180017082  mov     rax, [rdx]
0x180017085  mov     [rsi+18h], rax
0x180017089  add     qword ptr [rcx+8], 8
0x18001708e  jmp     loc_1800173F0
0x180017093  mov     byte ptr [rcx+18h], 1
0x180017097  jmp     loc_1800173F0
0x18001709c  lea     rax, aValue; "value"
0x1800170a3  mov     byte ptr [rdi+18h], 5
0x1800170a7  mov     rcx, rdi; this
0x1800170aa  mov     [rdi+10h], rax
0x1800170ae  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x1800170b3  test    al, al
0x1800170b5  jz      short loc_180017109
0x1800170b7  mov     rcx, [rdi]
0x1800170ba  mov     rdx, [rcx+8]
0x1800170be  cmp     rdx, [rcx+10h]
0x1800170c2  jnb     short loc_1800170E5
0x1800170c4  lea     rax, [rdx+1]
0x1800170c8  mov     [rcx+8], rax
0x1800170cc  test    rdx, rdx
0x1800170cf  jz      short loc_1800170E9
0x1800170d1  cmp     byte ptr [rdx], 11h
0x1800170d4  jz      short loc_1800170E9
0x1800170d6  cmp     [rdi+8], r14d
0x1800170da  jl      short loc_1800170E9
0x1800170dc  mov     dword ptr [rdi+8], 8007065Dh
0x1800170e3  jmp     short loc_1800170E9
0x1800170e5  mov     byte ptr [rcx+18h], 1
0x1800170e9  mov     rcx, [rdi]
0x1800170ec  mov     rdx, [rcx+8]
0x1800170f0  lea     rax, [rdx+4]
0x1800170f4  cmp     rax, [rcx+10h]
0x1800170f8  ja      short loc_180017093
0x1800170fa  mov     eax, [rdx]
0x1800170fc  mov     [rsi+18h], eax
0x1800170ff  add     qword ptr [rcx+8], 4
0x180017104  jmp     loc_1800173F0
0x180017109  xor     eax, eax
0x18001710b  mov     [rsi+18h], eax
0x18001710e  jmp     loc_1800173F0
0x180017113  lea     rax, aValue; "value"
0x18001711a  mov     byte ptr [rdi+18h], 5
0x18001711e  mov     rcx, rdi; this
0x180017121  mov     [rdi+10h], rax
0x180017125  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x18001712a  test    al, al
0x18001712c  jz      short loc_180017186
0x18001712e  mov     rcx, [rdi]
0x180017131  mov     rdx, [rcx+8]
0x180017135  cmp     rdx, [rcx+10h]
0x180017139  jnb     short loc_18001715C
0x18001713b  lea     rax, [rdx+1]
0x18001713f  mov     [rcx+8], rax
0x180017143  test    rdx, rdx
0x180017146  jz      short loc_180017160
0x180017148  cmp     byte ptr [rdx], 0Dh
0x18001714b  jz      short loc_180017160
0x18001714d  cmp     [rdi+8], r14d
0x180017151  jl      short loc_180017160
0x180017153  mov     dword ptr [rdi+8], 8007065Dh
0x18001715a  jmp     short loc_180017160
0x18001715c  mov     byte ptr [rcx+18h], 1
0x180017160  mov     rcx, [rdi]
0x180017163  mov     rdx, [rcx+8]
0x180017167  lea     rax, [rdx+2]
0x18001716b  cmp     rax, [rcx+10h]
0x18001716f  ja      loc_180017093
0x180017175  movzx   eax, word ptr [rdx]
0x180017178  mov     [rsi+18h], ax
0x18001717c  add     qword ptr [rcx+8], 2
0x180017181  jmp     loc_1800173F0
0x180017186  xor     eax, eax
0x180017188  mov     [rsi+18h], ax
0x18001718c  jmp     loc_1800173F0
0x180017191  lea     rax, aValue; "value"
0x180017198  mov     byte ptr [rdi+18h], 5
0x18001719c  mov     rcx, rdi; this
0x18001719f  mov     [rdi+10h], rax
0x1800171a3  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x1800171a8  test    al, al
0x1800171aa  jz      short loc_180017200
0x1800171ac  mov     rcx, [rdi]
0x1800171af  mov     rdx, [rcx+8]
0x1800171b3  cmp     rdx, [rcx+10h]
0x1800171b7  jnb     short loc_1800171DA
0x1800171b9  lea     rax, [rdx+1]
0x1800171bd  mov     [rcx+8], rax
0x1800171c1  test    rdx, rdx
0x1800171c4  jz      short loc_1800171DE
0x1800171c6  cmp     byte ptr [rdx], 0Ch
0x1800171c9  jz      short loc_1800171DE
0x1800171cb  cmp     [rdi+8], r14d
0x1800171cf  jl      short loc_1800171DE
0x1800171d1  mov     dword ptr [rdi+8], 8007065Dh
0x1800171d8  jmp     short loc_1800171DE
0x1800171da  mov     byte ptr [rcx+18h], 1
0x1800171de  mov     rdx, [rdi]
0x1800171e1  mov     rax, [rdx+8]
0x1800171e5  cmp     rax, [rdx+10h]
0x1800171e9  jnb     loc_180016FD0
0x1800171ef  mov     cl, [rax]
0x1800171f1  inc     rax
0x1800171f4  mov     [rdx+8], rax
0x1800171f8  mov     [rsi+18h], cl
0x1800171fb  jmp     loc_1800173F0
0x180017200  xor     eax, eax
0x180017202  mov     [rsi+18h], al
0x180017205  jmp     loc_1800173F0
0x18001720a  sub     ecx, 12h
0x18001720d  jz      loc_1800173CD
0x180017213  sub     ecx, 1
0x180017216  jz      loc_180017384
0x18001721c  sub     ecx, 1
0x18001721f  jz      loc_180017337
0x180017225  sub     ecx, 1
0x180017228  jz      loc_1800172F2
0x18001722e  sub     ecx, 9
0x180017231  jz      loc_1800172CA
0x180017237  cmp     ecx, 1
0x18001723a  jz      short loc_180017252
0x18001723c  cmp     [rdi+8], r14d
0x180017240  jl      loc_1800173F0
0x180017246  mov     dword ptr [rdi+8], 80070309h
0x18001724d  jmp     loc_1800173F0
0x180017252  lea     rax, aValue; "value"
0x180017259  mov     byte ptr [rdi+18h], 5
0x18001725d  mov     [rdi+10h], rax
0x180017261  lea     rdx, [rbp+var_50]; struct tson::string_tag *
0x180017265  xor     eax, eax
0x180017267  mov     [rbp+var_50], r14
0x18001726b  mov     rcx, rdi; this
0x18001726e  mov     dword ptr [rbp+var_40+1], eax
0x180017271  mov     word ptr [rbp+var_40+5], ax
0x180017275  mov     byte ptr [rbp+var_40+7], al
0x180017278  mov     [rbp+var_48], r14
0x18001727c  mov     byte ptr [rbp+var_40], r14b
0x180017280  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x180017285  mov     rcx, [rbp+var_48]
0x180017289  test    rcx, rcx
0x18001728c  jz      short loc_1800172BE
0x18001728e  add     rcx, rcx; cb
0x180017291  call    cs:__imp_CoTaskMemAlloc
0x180017297  mov     rbx, rax
0x18001729a  test    rax, rax
0x18001729d  jz      short loc_1800172B1
0x18001729f  lea     rdx, [rbp+var_50]; struct tson::string_tag *
0x1800172a3  mov     [rbp+var_50], rax
0x1800172a7  mov     rcx, rdi; this
0x1800172aa  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x1800172af  jmp     short loc_1800172C1
0x1800172b1  cmp     [rdi+8], r14d
0x1800172b5  jl      short loc_1800172BE
0x1800172b7  mov     dword ptr [rdi+8], 8007000Eh
0x1800172be  mov     rbx, r14
0x1800172c1  mov     [rsi+18h], rbx
0x1800172c5  jmp     loc_1800173F0
0x1800172ca  lea     rax, aValue; "value"
0x1800172d1  mov     [rbp+arg_8], r14
0x1800172d5  lea     rdx, [rbp+arg_8]
0x1800172d9  mov     [rdi+10h], rax
0x1800172dd  mov     rcx, rdi; this
0x1800172e0  mov     byte ptr [rdi+18h], 5
0x1800172e4  call    ??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x1800172e9  mov     rax, [rbp+arg_8]
0x1800172ed  jmp     loc_18001737E
0x1800172f2  lea     rax, aValue; "value"
0x1800172f9  mov     byte ptr [rdi+18h], 5
0x1800172fd  mov     rcx, rdi; this
0x180017300  mov     [rdi+10h], rax
0x180017304  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
  ... truncated ...
```
