# FIsThisTheNodeNameWithNamespace(IXMLDOMNode *,ushort const *,ushort const *,ulong,int)

- ea: `0x180009d2c`
- end: `0x180009f5d`
- name: `?FIsThisTheNodeNameWithNamespace@@YAHPEAUIXMLDOMNode@@PEBG1KH@Z`
- size: `561`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009420`

## callees

- `0x180001400`
- `0x1800038ec`
- `0x180009d2c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180009eb5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180009ecb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180009eb5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180009ecb`
- `OLEAUT32!__imp_SysFreeString` at `0x180009ee0`
- `OLEAUT32!__imp_SysFreeString` at `0x180009eeb`
- `OLEAUT32!__imp_SysFreeString` at `0x180009ee0`
- `OLEAUT32!__imp_SysFreeString` at `0x180009eeb`

## string_xrefs

- `0x180009e06`: `http://schemas.xmlsoap.org/soap/envelope/`

## pseudocode

```c
__int64 __fastcall FIsThisTheNodeNameWithNamespace(
        struct IXMLDOMNode *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned int v5; // esi
  signed int v6; // ebx
  OLECHAR *v7; // r8
  __int64 v8; // rcx
  BSTR v9; // rax
  __int64 v10; // r11
  const wchar_t *v11; // rcx
  __int64 v12; // r9
  WCHAR *v13; // r10
  __int64 v14; // rax
  __int64 v15; // rdx
  WCHAR *v16; // rcx
  OLECHAR *v17; // rcx
  WCHAR *v18; // rax
  WCHAR *v19; // rcx
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpString1; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR String2[256]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String1[256]; // [rsp+240h] [rbp+140h] BYREF

  lpString1 = 0;
  bstrString = 0;
  v5 = 0;
  if ( !a2 )
  {
    LOBYTE(v6) = 87;
LABEL_33:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
        (unsigned int)"FIsThisTheNodeNameWithNamespace(): Exiting",
        v6);
    return v5;
  }
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, LPCWSTR *, const unsigned __int16 *))a1->lpVtbl->get_baseName)(
         a1,
         &lpString1,
         a3);
  if ( v6 >= 0 && lpString1 )
  {
    v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))a1->lpVtbl->get_namespaceURI)(a1, &bstrString);
    if ( v6 >= 0 )
    {
      v7 = bstrString;
      if ( bstrString )
      {
        v8 = 0x7FFFFFFF;
        v9 = bstrString;
        do
        {
          if ( !*v9 )
            break;
          ++v9;
          --v8;
        }
        while ( v8 );
        v6 = v8 == 0 ? 0x80070057 : 0;
        if ( v8 )
        {
          v10 = 41;
          v11 = L"http://schemas.xmlsoap.org/soap/envelope/";
          v12 = 256;
          v13 = String1;
          v14 = 41;
          v15 = 256;
          do
          {
            if ( !v14 )
              break;
            if ( !*v11 )
              break;
            *v13++ = *v11++;
            --v14;
            --v15;
          }
          while ( v15 );
          v16 = v13 - 1;
          v6 = v15 == 0 ? 0x8007007A : 0;
          if ( v15 )
            v16 = v13;
          *v16 = 0;
          if ( v15 )
          {
            v17 = v7;
            v18 = String2;
            do
            {
              if ( !v10 )
                break;
              if ( !*v17 )
                break;
              *v18++ = *v17++;
              --v10;
              --v12;
            }
            while ( v12 );
            v19 = v18 - 1;
            if ( v12 )
              v19 = v18;
            *v19 = 0;
            v6 = v12 == 0 ? 0x8007007A : 0;
            if ( v12 )
            {
              if ( !lstrcmpW(lpString1, a2) && !lstrcmpW(String1, String2) )
                v5 = 1;
              v7 = bstrString;
            }
          }
        }
        SysFreeString(v7);
      }
    }
    SysFreeString((BSTR)lpString1);
  }
  if ( v6 )
    goto LABEL_33;
  return v5;
}

```

## disassembly

```asm
0x180009d2c  mov     [rsp-8+arg_10], rbx
0x180009d31  push    rbp
0x180009d32  push    rsi
0x180009d33  push    rdi
0x180009d34  push    r14
0x180009d36  push    r15
0x180009d38  lea     rbp, [rsp-350h]
0x180009d40  sub     rsp, 450h
0x180009d47  mov     rax, cs:__security_cookie
0x180009d4e  xor     rax, rsp
0x180009d51  mov     [rbp+370h+var_30], rax
0x180009d58  xor     r15d, r15d
0x180009d5b  mov     r14, rdx
0x180009d5e  mov     [rsp+470h+lpString1], r15
0x180009d63  mov     rdi, rcx
0x180009d66  mov     [rsp+470h+bstrString], r15
0x180009d6b  mov     esi, r15d
0x180009d6e  test    rdx, rdx
0x180009d71  jz      loc_180009EF7
0x180009d77  mov     rax, [rcx]
0x180009d7a  lea     rdx, [rsp+470h+lpString1]
0x180009d7f  mov     rax, [rax+148h]
0x180009d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d8b  mov     ebx, eax
0x180009d8d  test    eax, eax
0x180009d8f  js      loc_180009EF1
0x180009d95  cmp     [rsp+470h+lpString1], r15
0x180009d9a  jz      loc_180009EF1
0x180009da0  mov     rax, [rdi]
0x180009da3  lea     rdx, [rsp+470h+bstrString]
0x180009da8  mov     rcx, rdi
0x180009dab  mov     rax, [rax+138h]
0x180009db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009db7  mov     ebx, eax
0x180009db9  test    eax, eax
0x180009dbb  js      loc_180009EE6
0x180009dc1  mov     r8, [rsp+470h+bstrString]
0x180009dc6  test    r8, r8
0x180009dc9  jz      loc_180009EE6
0x180009dcf  mov     ecx, 7FFFFFFFh
0x180009dd4  mov     rax, r8
0x180009dd7  cmp     [rax], r15w
0x180009ddb  jz      short loc_180009DE7
0x180009ddd  add     rax, 2
0x180009de1  sub     rcx, 1
0x180009de5  jnz     short loc_180009DD7
0x180009de7  mov     rax, rcx
0x180009dea  neg     rax
0x180009ded  sbb     ebx, ebx
0x180009def  not     ebx
0x180009df1  and     ebx, 80070057h
0x180009df7  test    rcx, rcx
0x180009dfa  jz      loc_180009EDD
0x180009e00  mov     r11d, 29h ; ')'
0x180009e06  lea     rcx, aHttpSchemasXml_1; "http://schemas.xmlsoap.org/soap/envelop"...
0x180009e0d  mov     r9d, 100h
0x180009e13  lea     r10, [rbp+370h+String1]
0x180009e1a  mov     eax, r11d
0x180009e1d  mov     edx, r9d
0x180009e20  test    rax, rax
0x180009e23  jz      short loc_180009E42
0x180009e25  movzx   ebx, word ptr [rcx]
0x180009e28  test    bx, bx
0x180009e2b  jz      short loc_180009E42
0x180009e2d  mov     [r10], bx
0x180009e31  add     rcx, 2
0x180009e35  add     r10, 2
0x180009e39  dec     rax
0x180009e3c  sub     rdx, 1
0x180009e40  jnz     short loc_180009E20
0x180009e42  mov     rax, rdx
0x180009e45  lea     rcx, [r10-2]
0x180009e49  neg     rax
0x180009e4c  mov     edi, 8007007Ah
0x180009e51  sbb     ebx, ebx
0x180009e53  not     ebx
0x180009e55  and     ebx, edi
0x180009e57  test    rdx, rdx
0x180009e5a  cmovnz  rcx, r10
0x180009e5e  mov     [rcx], r15w
0x180009e62  jz      short loc_180009EDD
0x180009e64  mov     rcx, r8
0x180009e67  lea     rax, [rsp+470h+String2]
0x180009e6c  test    r11, r11
0x180009e6f  jz      short loc_180009E8D
0x180009e71  movzx   edx, word ptr [rcx]
0x180009e74  test    dx, dx
0x180009e77  jz      short loc_180009E8D
0x180009e79  mov     [rax], dx
0x180009e7c  add     rcx, 2
0x180009e80  add     rax, 2
0x180009e84  dec     r11
0x180009e87  sub     r9, 1
0x180009e8b  jnz     short loc_180009E6C
0x180009e8d  test    r9, r9
0x180009e90  lea     rcx, [rax-2]
0x180009e94  cmovnz  rcx, rax
0x180009e98  mov     rax, r9
0x180009e9b  neg     rax
0x180009e9e  sbb     ebx, ebx
0x180009ea0  not     ebx
0x180009ea2  mov     [rcx], r15w
0x180009ea6  and     ebx, edi
0x180009ea8  test    r9, r9
0x180009eab  jz      short loc_180009EDD
0x180009ead  mov     rcx, [rsp+470h+lpString1]; lpString1
0x180009eb2  mov     rdx, r14; lpString2
0x180009eb5  call    cs:__imp_lstrcmpW
0x180009ebb  test    eax, eax
0x180009ebd  jnz     short loc_180009ED8
0x180009ebf  lea     rdx, [rsp+470h+String2]; lpString2
0x180009ec4  lea     rcx, [rbp+370h+String1]; lpString1
0x180009ecb  call    cs:__imp_lstrcmpW
0x180009ed1  test    eax, eax
0x180009ed3  jnz     short loc_180009ED8
0x180009ed5  lea     esi, [rax+1]
0x180009ed8  mov     r8, [rsp+470h+bstrString]
0x180009edd  mov     rcx, r8; bstrString
0x180009ee0  call    cs:__imp_SysFreeString
0x180009ee6  mov     rcx, [rsp+470h+lpString1]; bstrString
0x180009eeb  call    cs:__imp_SysFreeString
0x180009ef1  test    ebx, ebx
0x180009ef3  jz      short loc_180009F35
0x180009ef5  jmp     short loc_180009EFC
0x180009ef7  mov     ebx, 80070057h
0x180009efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f03  lea     rax, WPP_GLOBAL_Control
0x180009f0a  cmp     rcx, rax
0x180009f0d  jz      short loc_180009F35
0x180009f0f  test    byte ptr [rcx+1Ch], 1
0x180009f13  jz      short loc_180009F35
0x180009f15  mov     rcx, [rcx+10h]
0x180009f19  lea     r9, aFisthisthenode; "FIsThisTheNodeNameWithNamespace(): Exit"...
0x180009f20  mov     edx, 14h
0x180009f25  mov     [rsp+470h+var_450], ebx
0x180009f29  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x180009f30  call    WPP_SF_sd
0x180009f35  mov     eax, esi
0x180009f37  mov     rcx, [rbp+370h+var_30]
0x180009f3e  xor     rcx, rsp; StackCookie
0x180009f41  call    __security_check_cookie
0x180009f46  mov     rbx, [rsp+470h+arg_10]
0x180009f4e  add     rsp, 450h
0x180009f55  pop     r15
0x180009f57  pop     r14
0x180009f59  pop     rdi
0x180009f5a  pop     rsi
0x180009f5b  pop     rbp
0x180009f5c  retn
```
