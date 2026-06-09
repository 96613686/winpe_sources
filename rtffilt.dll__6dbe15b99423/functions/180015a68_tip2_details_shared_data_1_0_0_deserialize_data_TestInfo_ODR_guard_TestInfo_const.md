# tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)

- ea: `0x180015a68`
- end: `0x180015e1a`
- name: `?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z`
- size: `946`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800156e4`
- `0x180015820`
- `0x180015e20`
- `0x18001779c`

## callees

- `0x180001e40`
- `0x1800028b4`
- `0x18000dc28`
- `0x18000de78`
- `0x180015a68`
- `0x180018644`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<1,0,0>::deserialize_data(__int64 *a1, __int64 a2)
{
  int *v4; // r8
  unsigned int v5; // ecx
  char v6; // si
  int *v7; // rcx
  int v8; // eax
  int *v9; // rdx
  int v10; // eax
  __int64 v11; // rax
  int *v12; // rdx
  int v13; // eax
  unsigned __int8 *v14; // rax
  __int16 v15; // cx
  __int16 v16; // r8
  int *v17; // rax
  __int16 v18; // dx
  unsigned __int64 v19; // rdx
  int *v20; // rcx
  __int64 v21; // rcx
  int *v22; // [rsp+30h] [rbp-D0h] BYREF
  int *v23; // [rsp+38h] [rbp-C8h]
  int *v24; // [rsp+40h] [rbp-C0h]
  char v25; // [rsp+48h] [rbp-B8h]
  const char *v26; // [rsp+50h] [rbp-B0h]
  char v27; // [rsp+58h] [rbp-A8h]
  __int64 *v28; // [rsp+60h] [rbp-A0h]
  const char *v29; // [rsp+68h] [rbp-98h]
  char v30; // [rsp+70h] [rbp-90h]
  __int64 *v31; // [rsp+78h] [rbp-88h]
  const char *v32; // [rsp+80h] [rbp-80h]
  char v33; // [rsp+88h] [rbp-78h]
  __int64 *v34; // [rsp+90h] [rbp-70h]
  int **v35; // [rsp+A0h] [rbp-60h] BYREF
  int v36; // [rsp+A8h] [rbp-58h]
  const char *v37; // [rsp+B0h] [rbp-50h]
  __int16 v38; // [rsp+B8h] [rbp-48h]
  char v39; // [rsp+C0h] [rbp-40h]
  _DWORD v40[25]; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned __int64 v41; // [rsp+128h] [rbp+28h]

  if ( (*(_DWORD *)(a2 + 20) & 0x1000) == 0 )
    goto LABEL_66;
  v4 = *(int **)(a2 + 24);
  v22 = v4;
  v23 = v4;
  v24 = v4;
  v25 = 0;
  if ( v4
    && *(_BYTE *)v4
    && *((_BYTE *)v4 + 1)
    && *((_BYTE *)v4 + 2)
    && *((_BYTE *)v4 + 3)
    && !*((_BYTE *)v4 + 4)
    && (*v4 & 0xC0C0C0C0) == 0x80408040 )
  {
    v5 = *v4;
    v23 = (int *)((char *)v4 + 5);
    v24 = (int *)((char *)v4
                + (v5 & 0x3F | ((v5 & 0x3F00 | ((v5 & 0x3F0000 | (unsigned __int64)((v5 >> 2) & 0xFC00000)) >> 2)) >> 2)));
  }
  else
  {
    v25 = 1;
  }
  v6 = *((_BYTE *)a1 + 33);
  v35 = &v22;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  memset_0(v40, 0, sizeof(v40));
  v41 = 0;
  v7 = v35[1];
  if ( v7 >= v35[2] )
  {
    *((_BYTE *)v35 + 24) = 1;
  }
  else
  {
    v35[1] = (int *)((char *)v7 + 1);
    if ( v7 && *(_BYTE *)v7 != 0x80 )
    {
      v8 = v36;
      if ( v36 >= 0 )
        v8 = -2147024119;
      v36 = v8;
    }
  }
  v9 = v35[1];
  if ( v9 >= v35[2] )
  {
    *((_BYTE *)v35 + 24) = 1;
  }
  else
  {
    v35[1] = (int *)((char *)v9 + 1);
    if ( v9 && v6 != *(_BYTE *)v9 )
    {
      v10 = v36;
      if ( v36 >= 0 )
        v10 = -2147024119;
      v36 = v10;
    }
  }
  if ( v41 >= 0x19 )
    v39 = 1;
  else
    v40[v41++] = 0;
  if ( (*((_DWORD *)a1 + 5) & 0x40000) != 0 )
  {
    LOBYTE(v38) = 4;
    v37 = "name";
    if ( a1[3] )
    {
      if ( tson::input_archive::search((tson::input_archive *)&v35) )
      {
        v12 = v35[1];
        if ( v12 >= v35[2] )
        {
          *((_BYTE *)v35 + 24) = 1;
        }
        else
        {
          v35[1] = (int *)((char *)v12 + 1);
          if ( v12 && *(_BYTE *)v12 != 23 )
          {
            v13 = v36;
            if ( v36 >= 0 )
              v13 = -2147023267;
            v36 = v13;
          }
        }
        v14 = (unsigned __int8 *)v35[1];
        if ( v14 >= (unsigned __int8 *)v35[2] )
        {
          *((_BYTE *)v35 + 24) = 1;
        }
        else
        {
          v15 = *v14;
          v35[1] = (int *)(v14 + 1);
          if ( (unsigned __int8)v15 > 1u )
          {
            if ( (v15 & 0x80u) == 0 )
            {
              v18 = v15;
            }
            else
            {
              v16 = v15 & 0x7F;
              v17 = v35[1];
              if ( v17 >= v35[2] )
              {
                *((_BYTE *)v35 + 24) = 1;
              }
              else
              {
                LOBYTE(v15) = *(_BYTE *)v17;
                v35[1] = (int *)((char *)v17 + 1);
              }
              v18 = (unsigned __int8)v15 | (unsigned __int16)(v16 << 8);
            }
            v19 = (unsigned __int64)v35[1] + (unsigned __int16)(v18 - 1);
            if ( v19 > (unsigned __int64)v35[2] )
              *((_BYTE *)v35 + 24) = 1;
            else
              v35[1] = (int *)v19;
          }
        }
      }
    }
    else
    {
      tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(
        (tson::input_archive *)&v35,
        (void **)a1 + 1);
      v11 = a1[1];
      if ( v11 )
        a1[3] = v11;
    }
  }
  v26 = "flags";
  v27 = 5;
  v28 = a1 + 15;
  v29 = "errors";
  v30 = 6;
  v31 = a1 + 9;
  v32 = "log";
  v33 = 3;
  v34 = a1 + 12;
  tson::input_archive::operator()<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson *)&v35);
  v20 = v35[1];
  if ( v20 < v35[2] && *(_BYTE *)v20 == 8 )
  {
    v35[1] = (int *)((char *)v20 + 1);
    if ( *(_BYTE *)v20 != 8 )
    {
      if ( v36 < 0 )
        goto LABEL_66;
      v36 = -2147023267;
    }
  }
  else
  {
    v21 = *a1;
    if ( tip2::details::g_test_interface_exception_guard )
    {
      if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v21, 0, 0, &v35, 0)
        && !*((_BYTE *)a1 + 160) )
      {
        *((_BYTE *)a1 + 160) = 3;
        *((_WORD *)a1 + 81) = 16397;
        a1[21] = 0;
      }
    }
    else
    {
      (*(void (__fastcall **)(__int64, int ***))(*(_QWORD *)v21 + 16LL))(v21, &v35);
    }
  }
  if ( v36 >= 0 && !*((_BYTE *)v35 + 24) && !v39 )
  {
    *((_DWORD *)a1 + 46) = *(_DWORD *)(a2 + 16);
    return;
  }
LABEL_66:
  *((_DWORD *)a1 + 16) |= 0x80000u;
}

```

## disassembly

```asm
0x180015a68  push    rbp
0x180015a6a  push    rbx
0x180015a6b  push    rsi
0x180015a6c  push    rdi
0x180015a6d  push    r14
0x180015a6f  push    r15
0x180015a71  lea     rbp, [rsp-48h]
0x180015a76  sub     rsp, 148h
0x180015a7d  mov     rax, cs:__security_cookie
0x180015a84  xor     rax, rsp
0x180015a87  mov     [rbp+70h+var_40], rax
0x180015a8b  mov     r14, rdx
0x180015a8e  mov     rbx, rcx
0x180015a91  test    dword ptr [rdx+14h], 1000h
0x180015a98  jz      loc_180015DF9
0x180015a9e  mov     r8, [rdx+18h]
0x180015aa2  mov     [rsp+170h+var_140], r8
0x180015aa7  mov     [rsp+170h+var_138], r8
0x180015aac  mov     [rsp+170h+var_130], r8
0x180015ab1  xor     r15d, r15d
0x180015ab4  mov     [rsp+170h+var_128], r15b
0x180015ab9  test    r8, r8
0x180015abc  jz      short loc_180015B2E
0x180015abe  cmp     [r8], r15b
0x180015ac1  jz      short loc_180015B2E
0x180015ac3  cmp     [r8+1], r15b
0x180015ac7  jz      short loc_180015B2E
0x180015ac9  cmp     [r8+2], r15b
0x180015acd  jz      short loc_180015B2E
0x180015acf  cmp     [r8+3], r15b
0x180015ad3  jz      short loc_180015B2E
0x180015ad5  cmp     [r8+4], r15b
0x180015ad9  jnz     short loc_180015B2E
0x180015adb  mov     eax, [r8]
0x180015ade  and     eax, 0C0C0C0C0h
0x180015ae3  cmp     eax, 80408040h
0x180015ae8  jnz     short loc_180015B2E
0x180015aea  mov     ecx, [r8]
0x180015aed  lea     rax, [r8+5]
0x180015af1  mov     [rsp+170h+var_138], rax
0x180015af6  mov     edx, ecx
0x180015af8  shr     rdx, 2
0x180015afc  and     edx, 0FC00000h
0x180015b02  mov     eax, ecx
0x180015b04  and     eax, 3F0000h
0x180015b09  or      rdx, rax
0x180015b0c  shr     rdx, 2
0x180015b10  mov     eax, ecx
0x180015b12  and     eax, 3F00h
0x180015b17  or      rdx, rax
0x180015b1a  shr     rdx, 2
0x180015b1e  and     ecx, 3Fh
0x180015b21  or      rdx, rcx
0x180015b24  add     rdx, r8
0x180015b27  mov     [rsp+170h+var_130], rdx
0x180015b2c  jmp     short loc_180015B33
0x180015b2e  mov     [rsp+170h+var_128], 1
0x180015b33  mov     sil, [rbx+21h]
0x180015b37  lea     rax, [rsp+170h+var_140]
0x180015b3c  mov     [rbp+70h+var_D0], rax
0x180015b40  mov     [rbp+70h+var_C8], r15d
0x180015b44  mov     [rbp+70h+var_C0], r15
0x180015b48  mov     [rbp+70h+var_B8], r15w
0x180015b4d  mov     [rbp+70h+var_B0], r15b
0x180015b51  xor     edx, edx; Val
0x180015b53  lea     r8d, [rdx+64h]; Size
0x180015b57  lea     rcx, [rbp+70h+var_AC]; void *
0x180015b5b  call    memset_0
0x180015b60  mov     [rbp+70h+var_48], r15
0x180015b64  mov     rdx, [rbp+70h+var_D0]
0x180015b68  mov     rcx, [rdx+8]
0x180015b6c  mov     r8d, 80070309h
0x180015b72  cmp     rcx, [rdx+10h]
0x180015b76  jnb     short loc_180015B98
0x180015b78  lea     rax, [rcx+1]
0x180015b7c  mov     [rdx+8], rax
0x180015b80  test    rcx, rcx
0x180015b83  jz      short loc_180015B9C
0x180015b85  cmp     byte ptr [rcx], 80h
0x180015b88  jz      short loc_180015B9C
0x180015b8a  mov     eax, [rbp+70h+var_C8]
0x180015b8d  test    eax, eax
0x180015b8f  cmovns  eax, r8d
0x180015b93  mov     [rbp+70h+var_C8], eax
0x180015b96  jmp     short loc_180015B9C
0x180015b98  mov     byte ptr [rdx+18h], 1
0x180015b9c  mov     rcx, [rbp+70h+var_D0]
0x180015ba0  mov     rdx, [rcx+8]
0x180015ba4  cmp     rdx, [rcx+10h]
0x180015ba8  jnb     short loc_180015BCA
0x180015baa  lea     rax, [rdx+1]
0x180015bae  mov     [rcx+8], rax
0x180015bb2  test    rdx, rdx
0x180015bb5  jz      short loc_180015BCE
0x180015bb7  cmp     sil, [rdx]
0x180015bba  jz      short loc_180015BCE
0x180015bbc  mov     eax, [rbp+70h+var_C8]
0x180015bbf  test    eax, eax
0x180015bc1  cmovns  eax, r8d
0x180015bc5  mov     [rbp+70h+var_C8], eax
0x180015bc8  jmp     short loc_180015BCE
0x180015bca  mov     byte ptr [rcx+18h], 1
0x180015bce  mov     rax, [rbp+70h+var_48]
0x180015bd2  cmp     rax, 19h
0x180015bd6  jnb     short loc_180015BE3
0x180015bd8  mov     [rbp+rax*4+70h+var_AC], r15d
0x180015bdd  inc     [rbp+70h+var_48]
0x180015be1  jmp     short loc_180015BE7
0x180015be3  mov     [rbp+70h+var_B0], 1
0x180015be7  mov     esi, 8007065Dh
0x180015bec  test    dword ptr [rbx+14h], 40000h
0x180015bf3  jz      loc_180015CED
0x180015bf9  lea     rax, aName; "name"
0x180015c00  mov     byte ptr [rbp+70h+var_B8], 4
0x180015c04  lea     rcx, [rbp+70h+var_D0]; this
0x180015c08  mov     [rbp+70h+var_C0], rax
0x180015c0c  cmp     [rbx+18h], r15
0x180015c10  jnz     short loc_180015C31
0x180015c12  lea     rdx, [rbx+8]
0x180015c16  call    ??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x180015c1b  mov     rax, [rbx+8]
0x180015c1f  test    rax, rax
0x180015c22  jz      loc_180015CED
0x180015c28  mov     [rbx+18h], rax
0x180015c2c  jmp     loc_180015CED
0x180015c31  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x180015c36  test    al, al
0x180015c38  jz      loc_180015CED
0x180015c3e  mov     rcx, [rbp+70h+var_D0]
0x180015c42  mov     rdx, [rcx+8]
0x180015c46  cmp     rdx, [rcx+10h]
0x180015c4a  jnb     short loc_180015C6B
0x180015c4c  lea     rax, [rdx+1]
0x180015c50  mov     [rcx+8], rax
0x180015c54  test    rdx, rdx
0x180015c57  jz      short loc_180015C6F
0x180015c59  cmp     byte ptr [rdx], 17h
0x180015c5c  jz      short loc_180015C6F
0x180015c5e  mov     eax, [rbp+70h+var_C8]
0x180015c61  test    eax, eax
0x180015c63  cmovns  eax, esi
0x180015c66  mov     [rbp+70h+var_C8], eax
0x180015c69  jmp     short loc_180015C6F
0x180015c6b  mov     byte ptr [rcx+18h], 1
0x180015c6f  mov     rdx, [rbp+70h+var_D0]
0x180015c73  mov     rax, [rdx+8]
0x180015c77  cmp     rax, [rdx+10h]
0x180015c7b  jnb     short loc_180015CE9
0x180015c7d  movzx   ecx, byte ptr [rax]
0x180015c80  inc     rax
0x180015c83  mov     [rdx+8], rax
0x180015c87  cmp     cl, 1
0x180015c8a  jbe     short loc_180015CED
0x180015c8c  test    cl, cl
0x180015c8e  jns     short loc_180015CC4
0x180015c90  mov     al, cl
0x180015c92  and     al, 7Fh
0x180015c94  movzx   r8d, al
0x180015c98  mov     rdx, [rbp+70h+var_D0]
0x180015c9c  mov     rax, [rdx+8]
0x180015ca0  cmp     rax, [rdx+10h]
0x180015ca4  jnb     short loc_180015CB1
0x180015ca6  mov     cl, [rax]
0x180015ca8  inc     rax
0x180015cab  mov     [rdx+8], rax
0x180015caf  jmp     short loc_180015CB5
0x180015cb1  mov     byte ptr [rdx+18h], 1
0x180015cb5  mov     rdx, r8
0x180015cb8  shl     rdx, 8
0x180015cbc  movzx   eax, cl
0x180015cbf  or      rdx, rax
0x180015cc2  jmp     short loc_180015CC7
0x180015cc4  mov     rdx, rcx
0x180015cc7  mov     r8, [rbp+70h+var_D0]
0x180015ccb  lea     rax, [rdx-1]
0x180015ccf  movzx   edx, ax
0x180015cd2  add     rdx, [r8+8]
0x180015cd6  cmp     rdx, [r8+10h]
0x180015cda  ja      short loc_180015CE2
0x180015cdc  mov     [r8+8], rdx
0x180015ce0  jmp     short loc_180015CED
0x180015ce2  mov     byte ptr [r8+18h], 1
0x180015ce7  jmp     short loc_180015CED
0x180015ce9  mov     byte ptr [rdx+18h], 1
0x180015ced  lea     rax, aFlags; "flags"
0x180015cf4  mov     [rsp+170h+var_120], rax
0x180015cf9  mov     [rsp+170h+var_118], 5
0x180015cfe  lea     rax, [rbx+78h]
0x180015d02  mov     [rsp+170h+var_110], rax
0x180015d07  lea     rax, aErrors; "errors"
0x180015d0e  mov     [rsp+170h+var_108], rax
0x180015d13  mov     [rsp+170h+var_100], 6
0x180015d18  lea     rax, [rbx+48h]
0x180015d1c  mov     [rsp+170h+var_F8], rax
0x180015d21  lea     rax, aLog; "log"
0x180015d28  mov     [rbp+70h+var_F0], rax
0x180015d2c  mov     [rbp+70h+var_E8], 3
0x180015d30  lea     rax, [rbx+60h]
0x180015d34  mov     [rbp+70h+var_E0], rax
0x180015d38  lea     r9, [rsp+170h+var_120]
0x180015d3d  lea     r8, [rsp+170h+var_108]
0x180015d42  lea     rdx, [rbp+70h+var_F0]
0x180015d46  lea     rcx, [rbp+70h+var_D0]; this
0x180015d4a  call    ??$?RV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::input_archive::operator()<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x180015d4f  mov     rdx, [rbp+70h+var_D0]
0x180015d53  mov     rcx, [rdx+8]
0x180015d57  cmp     rcx, [rdx+10h]
0x180015d5b  jnb     short loc_180015D7E
0x180015d5d  cmp     byte ptr [rcx], 8
0x180015d60  jnz     short loc_180015D7E
0x180015d62  lea     rax, [rcx+1]
0x180015d66  mov     [rdx+8], rax
0x180015d6a  cmp     byte ptr [rcx], 8
0x180015d6d  jz      short loc_180015DD7
0x180015d6f  cmp     [rbp+70h+var_C8], r15d
0x180015d73  jl      loc_180015DF9
0x180015d79  mov     [rbp+70h+var_C8], esi
0x180015d7c  jmp     short loc_180015DD7
0x180015d7e  mov     rcx, [rbx]
0x180015d81  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180015d88  test    rax, rax
0x180015d8b  jz      short loc_180015DC6
0x180015d8d  mov     [rsp+170h+var_150], r15
0x180015d92  lea     r9, [rbp+70h+var_D0]
0x180015d96  xor     r8d, r8d
0x180015d99  xor     edx, edx
0x180015d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015da0  test    al, al
0x180015da2  jnz     short loc_180015DD7
0x180015da4  cmp     [rbx+0A0h], r15b
0x180015dab  jnz     short loc_180015DD7
0x180015dad  mov     byte ptr [rbx+0A0h], 3
0x180015db4  mov     word ptr [rbx+0A2h], 400Dh
0x180015dbd  mov     [rbx+0A8h], r15
0x180015dc4  jmp     short loc_180015DD7
0x180015dc6  mov     rax, [rcx]
0x180015dc9  lea     rdx, [rbp+70h+var_D0]
0x180015dcd  mov     rax, [rax+10h]
0x180015dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dd6  nop
0x180015dd7  cmp     [rbp+70h+var_C8], r15d
0x180015ddb  jl      short loc_180015DF9
0x180015ddd  mov     rax, [rbp+70h+var_D0]
0x180015de1  cmp     [rax+18h], r15b
0x180015de5  jnz     short loc_180015DF9
0x180015de7  cmp     [rbp+70h+var_B0], r15b
0x180015deb  jnz     short loc_180015DF9
0x180015ded  mov     eax, [r14+10h]
0x180015df1  mov     [rbx+0B8h], eax
0x180015df7  jmp     short loc_180015DFE
0x180015df9  bts     dword ptr [rbx+40h], 13h
0x180015dfe  mov     rcx, [rbp+70h+var_40]
0x180015e02  xor     rcx, rsp; StackCookie
0x180015e05  call    __security_check_cookie
0x180015e0a  add     rsp, 148h
0x180015e11  pop     r15
0x180015e13  pop     r14
0x180015e15  pop     rdi
0x180015e16  pop     rsi
0x180015e17  pop     rbx
0x180015e18  pop     rbp
0x180015e19  retn
```
