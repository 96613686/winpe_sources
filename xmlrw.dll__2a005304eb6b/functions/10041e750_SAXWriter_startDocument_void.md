# SAXWriter::startDocument(void)

- ea: `0x10041e750`
- end: `0x10041eaeb`
- name: `?startDocument@SAXWriter@@UEAAJXZ`
- size: `923`
- prototype: `__int64 __fastcall(SAXWriter *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x100401780`
- `0x10041d130`
- `0x10041db90`
- `0x10041e750`
- `0x100439df0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x10041e9fd`
- `OLEAUT32!__imp_SysStringLen` at `0x10041e9fd`
- `OLEAUT32!__imp_VariantClear` at `0x10041e905`
- `OLEAUT32!__imp_VariantClear` at `0x10041e99c`
- `OLEAUT32!__imp_VariantClear` at `0x10041ea44`
- `OLEAUT32!__imp_VariantClear` at `0x10041e905`
- `OLEAUT32!__imp_VariantClear` at `0x10041e99c`
- `OLEAUT32!__imp_VariantClear` at `0x10041ea44`

## pseudocode

```c
__int64 __fastcall SAXWriter::startDocument(SAXWriter *this)
{
  unsigned int v2; // r14d
  unsigned int v3; // esi
  int (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rcx
  _WORD *v5; // rbx
  BSTR bstrVal; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // r10d
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rcx
  __int16 v13; // ax
  const OLECHAR *v14; // r8
  VARIANTARG pbstr; // [rsp+78h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-48h] BYREF
  VARIANTARG v18; // [rsp+A8h] [rbp-30h] BYREF
  __int64 v19; // [rsp+E8h] [rbp+10h] BYREF

  v2 = 0;
  v3 = 0;
  v19 = 0;
  if ( *((_DWORD *)this + 3) == 1 )
  {
    *((_DWORD *)this + 3) = 1;
  }
  else
  {
    v3 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 7) + 40LL))((char *)this - 56, 1);
    if ( v3 )
      goto LABEL_40;
  }
  *((_BYTE *)this + 16) = 0;
  if ( *((_BYTE *)this + 160) )
    SAXWriter::writeBOM((SAXWriter *)((char *)this - 56));
  if ( !*((_BYTE *)this + 168) )
  {
    v4 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 3);
    if ( !v4 || (**v4)(v4, &IID_ISAXXMLReader, &v19) < 0 )
    {
LABEL_37:
      v14 = L"1.0";
      if ( *((_WORD *)this + 58) )
        v14 = (const OLECHAR *)((char *)this + 116);
      LOBYTE(v2) = *((_DWORD *)this + 41) == 1;
      (*(void (__fastcall **)(char *, _QWORD, const OLECHAR *, _QWORD))(*((_QWORD *)this - 7) + 232LL))(
        (char *)this - 56,
        v2,
        v14,
        0);
      (*(void (__fastcall **)(char *))(*((_QWORD *)this - 7) + 56LL))((char *)this - 56);
      goto LABEL_40;
    }
    v5 = (_WORD *)((char *)this + 116);
    if ( !*((_WORD *)this + 58) )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v19 + 40LL))(
             v19,
             CodeStringPtr::xmlDeclVersion,
             &pvarg);
      if ( v3 )
        goto LABEL_40;
      bstrVal = pvarg.bstrVal;
      if ( pvarg.llVal )
      {
        v7 = 2147483646;
        v8 = 16;
        v9 = 0;
        v10 = 0;
        while ( v8 )
        {
          if ( !v7 || !*bstrVal )
            goto LABEL_19;
          *v5++ = *bstrVal++;
          --v8;
          --v7;
          ++v10;
        }
        --v5;
        v9 = -2147024774;
LABEL_19:
        *v5 = 0;
        if ( v9 < 0 )
        {
          MXRRaiseException(-2147024809);
          goto LABEL_44;
        }
        VariantClear(&pvarg);
      }
    }
    if ( **((_WORD **)this + 13) )
      goto LABEL_28;
    memset(&v18, 0, sizeof(v18));
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v19 + 40LL))(
           v19,
           CodeStringPtr::xmlDeclEncoding,
           &v18);
    if ( v3 )
      goto LABEL_40;
    if ( !v18.llVal )
    {
LABEL_28:
      if ( *((_DWORD *)this + 41) == -1 )
      {
        memset(&pbstr, 0, sizeof(pbstr));
        v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v19 + 40LL))(
               v19,
               CodeStringPtr::xmlDeclStandalone,
               &pbstr);
        if ( v3 )
          goto LABEL_40;
        if ( pbstr.llVal )
        {
          if ( SysStringLen(pbstr.bstrVal) == 3 )
          {
            v12 = 0;
            while ( 1 )
            {
              v13 = *(_WORD *)(pbstr.llVal + 2 * v12++);
              if ( v13 != aYes[v12 - 1] )
                break;
              if ( v12 == 4 )
              {
                *((_DWORD *)this + 41) = 1;
                break;
              }
            }
          }
          VariantClear(&pbstr);
        }
      }
      goto LABEL_37;
    }
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(v18.llVal + 2 * v11) );
    if ( (unsigned __int64)(v11 + 1) <= 0x18 )
    {
      SAXWriter::saveEncoding((SAXWriter *)((char *)this - 56), v18.bstrVal);
      VariantClear(&v18);
      goto LABEL_28;
    }
LABEL_44:
    MXRRaiseException(-2147024809);
    __debugbreak();
    JUMPOUT(0x10041EAEBLL);
  }
LABEL_40:
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return v3;
}

```

## disassembly

```asm
0x10041e750  mov     rax, rsp
0x10041e753  mov     [rax+8], rbx
0x10041e757  mov     [rax+18h], rsi
0x10041e75b  mov     [rax+20h], rdi
0x10041e75f  push    r14
0x10041e761  sub     rsp, 0D0h
0x10041e768  mov     rdi, rcx
0x10041e76b  xor     r14d, r14d
0x10041e76e  mov     esi, r14d
0x10041e771  mov     [rsp+0D8h+var_A8], r14d
0x10041e776  mov     [rax+10h], r14
0x10041e77a  cmp     dword ptr [rcx+0Ch], 1
0x10041e77e  jnz     short loc_10041E789
0x10041e780  mov     dword ptr [rcx+0Ch], 1
0x10041e787  jmp     short loc_10041E7AE
0x10041e789  mov     rax, [rcx-38h]
0x10041e78d  mov     edx, 1
0x10041e792  add     rcx, 0FFFFFFFFFFFFFFC8h
0x10041e796  mov     rax, [rax+28h]
0x10041e79a  call    cs:__guard_dispatch_icall_fptr
0x10041e7a0  mov     esi, eax
0x10041e7a2  mov     [rsp+0D8h+var_A8], eax
0x10041e7a6  test    eax, eax
0x10041e7a8  jnz     loc_10041EA9F
0x10041e7ae  mov     byte ptr [rdi+10h], 0
0x10041e7b2  cmp     byte ptr [rdi+0A0h], 0
0x10041e7b9  jz      short loc_10041E7C4
0x10041e7bb  lea     rcx, [rdi-38h]; this
0x10041e7bf  call    ?writeBOM@SAXWriter@@IEAAJXZ; SAXWriter::writeBOM(void)
0x10041e7c4  cmp     byte ptr [rdi+0A8h], 0
0x10041e7cb  jnz     loc_10041EA95
0x10041e7d1  mov     rcx, [rdi+18h]
0x10041e7d5  test    rcx, rcx
0x10041e7d8  jz      loc_10041EA4A
0x10041e7de  mov     rax, [rcx]
0x10041e7e1  lea     r8, [rsp+0D8h+arg_8]
0x10041e7e9  lea     rdx, IID_ISAXXMLReader
0x10041e7f0  mov     rax, [rax]
0x10041e7f3  call    cs:__guard_dispatch_icall_fptr
0x10041e7f9  test    eax, eax
0x10041e7fb  js      loc_10041EA4A
0x10041e801  lea     rbx, [rdi+74h]
0x10041e805  cmp     word ptr [rbx], 0
0x10041e809  jnz     loc_10041E90B
0x10041e80f  xorps   xmm0, xmm0
0x10041e812  xor     eax, eax
0x10041e814  movups  xmmword ptr [rsp+0D8h+pvarg], xmm0
0x10041e81c  mov     qword ptr [rsp+0D8h+pvarg+10h], rax
0x10041e824  mov     rcx, [rsp+0D8h+arg_8]
0x10041e82c  mov     rax, [rcx]
0x10041e82f  lea     r8, [rsp+0D8h+pvarg]
0x10041e837  mov     rdx, cs:?xmlDeclVersion@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::xmlDeclVersion
0x10041e83e  mov     rax, [rax+28h]
0x10041e842  call    cs:__guard_dispatch_icall_fptr
0x10041e848  mov     esi, eax
0x10041e84a  mov     [rsp+0D8h+var_A8], eax
0x10041e84e  test    eax, eax
0x10041e850  jnz     loc_10041EA9F
0x10041e856  mov     rax, qword ptr [rsp+0D8h+pvarg+8]
0x10041e85e  test    rax, rax
0x10041e861  jz      loc_10041E90B
0x10041e867  mov     edx, 7FFFFFFEh
0x10041e86c  mov     [rsp+0D8h+var_70], rdx
0x10041e871  mov     [rsp+0D8h+var_80], rax
0x10041e876  mov     ecx, 10h
0x10041e87b  mov     [rsp+0D8h+var_78], rcx
0x10041e880  mov     [rsp+0D8h+var_90], rbx
0x10041e885  mov     r10d, r14d
0x10041e888  mov     r8, r14
0x10041e88b  mov     [rsp+0D8h+var_88], r14
0x10041e890  test    rcx, rcx
0x10041e893  jz      short loc_10041E8D9
0x10041e895  test    rdx, rdx
0x10041e898  jz      short loc_10041E8D4
0x10041e89a  movzx   r9d, word ptr [rax]
0x10041e89e  test    r9w, r9w
0x10041e8a2  jz      short loc_10041E8D4
0x10041e8a4  mov     [rbx], r9w
0x10041e8a8  add     rbx, 2
0x10041e8ac  mov     [rsp+0D8h+var_90], rbx
0x10041e8b1  add     rax, 2
0x10041e8b5  mov     [rsp+0D8h+var_80], rax
0x10041e8ba  dec     rcx
0x10041e8bd  mov     [rsp+0D8h+var_78], rcx
0x10041e8c2  dec     rdx
0x10041e8c5  mov     [rsp+0D8h+var_70], rdx
0x10041e8ca  inc     r8
0x10041e8cd  mov     [rsp+0D8h+var_88], r8
0x10041e8d2  jmp     short loc_10041E890
0x10041e8d4  test    rcx, rcx
0x10041e8d7  jnz     short loc_10041E8F0
0x10041e8d9  sub     rbx, 2
0x10041e8dd  mov     [rsp+0D8h+var_90], rbx
0x10041e8e2  dec     r8
0x10041e8e5  mov     [rsp+0D8h+var_88], r8
0x10041e8ea  mov     r10d, 8007007Ah
0x10041e8f0  mov     [rbx], r14w
0x10041e8f4  test    r10d, r10d
0x10041e8f7  js      loc_10041EAD5
0x10041e8fd  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x10041e905  call    cs:__imp_VariantClear
0x10041e90b  mov     rax, [rdi+68h]
0x10041e90f  cmp     word ptr [rax], 0
0x10041e913  jnz     loc_10041E9A2
0x10041e919  xorps   xmm0, xmm0
0x10041e91c  xor     eax, eax
0x10041e91e  movups  xmmword ptr [rsp+0D8h+var_30], xmm0
0x10041e926  mov     qword ptr [rsp+0D8h+var_30+10h], rax
0x10041e92e  mov     rcx, [rsp+0D8h+arg_8]
0x10041e936  mov     rax, [rcx]
0x10041e939  lea     r8, [rsp+0D8h+var_30]
0x10041e941  mov     rdx, cs:?xmlDeclEncoding@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::xmlDeclEncoding
0x10041e948  mov     rax, [rax+28h]
0x10041e94c  call    cs:__guard_dispatch_icall_fptr
0x10041e952  mov     esi, eax
0x10041e954  mov     [rsp+0D8h+var_A8], eax
0x10041e958  test    eax, eax
0x10041e95a  jnz     loc_10041EA9F
0x10041e960  mov     rdx, qword ptr [rsp+0D8h+var_30+8]; wchar_t *
0x10041e968  test    rdx, rdx
0x10041e96b  jz      short loc_10041E9A2
0x10041e96d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x10041e974  inc     rax
0x10041e977  cmp     word ptr [rdx+rax*2], 0
0x10041e97c  jnz     short loc_10041E974
0x10041e97e  inc     rax
0x10041e981  cmp     rax, 18h
0x10041e985  ja      loc_10041EADF
0x10041e98b  lea     rcx, [rdi-38h]; this
0x10041e98f  call    ?saveEncoding@SAXWriter@@QEAAXPEB_W@Z; SAXWriter::saveEncoding(wchar_t const *)
0x10041e994  lea     rcx, [rsp+0D8h+var_30]; pvarg
0x10041e99c  call    cs:__imp_VariantClear
0x10041e9a2  cmp     dword ptr [rdi+0A4h], 0FFFFFFFFh
0x10041e9a9  jnz     loc_10041EA4A
0x10041e9af  xorps   xmm0, xmm0
0x10041e9b2  xor     eax, eax
0x10041e9b4  movups  xmmword ptr [rsp+0D8h+pbstr], xmm0
0x10041e9b9  mov     [rsp+0D8h+var_50], rax
0x10041e9c1  mov     rcx, [rsp+0D8h+arg_8]
0x10041e9c9  mov     rax, [rcx]
0x10041e9cc  lea     r8, [rsp+0D8h+pbstr]
0x10041e9d1  mov     rdx, cs:?xmlDeclStandalone@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::xmlDeclStandalone
0x10041e9d8  mov     rax, [rax+28h]
0x10041e9dc  call    cs:__guard_dispatch_icall_fptr
0x10041e9e2  mov     esi, eax
0x10041e9e4  mov     [rsp+0D8h+var_A8], eax
0x10041e9e8  test    eax, eax
0x10041e9ea  jnz     loc_10041EA9F
0x10041e9f0  mov     rcx, [rsp+0D8h+pbstr+8]; pbstr
0x10041e9f8  test    rcx, rcx
0x10041e9fb  jz      short loc_10041EA4A
0x10041e9fd  call    cs:__imp_SysStringLen
0x10041ea03  cmp     eax, 3
0x10041ea06  jnz     short loc_10041EA3F
0x10041ea08  mov     rcx, r14
0x10041ea0b  mov     rdx, [rsp+0D8h+pbstr+8]
0x10041ea13  lea     r8, aYes; "yes"
0x10041ea1a  nop     word ptr [rax+rax+00h]
0x10041ea20  movzx   eax, word ptr [rdx+rcx*2]
0x10041ea24  inc     rcx
0x10041ea27  cmp     ax, [r8+rcx*2-2]
0x10041ea2d  jnz     short loc_10041EA3F
0x10041ea2f  cmp     rcx, 4
0x10041ea33  jnz     short loc_10041EA20
0x10041ea35  mov     dword ptr [rdi+0A4h], 1
0x10041ea3f  lea     rcx, [rsp+0D8h+pbstr]; pvarg
0x10041ea44  call    cs:__imp_VariantClear
0x10041ea4a  lea     rax, [rdi+74h]
0x10041ea4e  lea     r8, psz; "1.0"
0x10041ea55  cmp     word ptr [rax], 0
0x10041ea59  cmovnz  r8, rax
0x10041ea5d  mov     rax, [rdi-38h]
0x10041ea61  cmp     dword ptr [rdi+0A4h], 1
0x10041ea68  setz    r14b
0x10041ea6c  xor     r9d, r9d
0x10041ea6f  mov     edx, r14d
0x10041ea72  lea     rcx, [rdi-38h]
0x10041ea76  mov     rax, [rax+0E8h]
0x10041ea7d  call    cs:__guard_dispatch_icall_fptr
0x10041ea83  mov     rax, [rdi-38h]
0x10041ea87  lea     rcx, [rdi-38h]
0x10041ea8b  mov     rax, [rax+38h]
0x10041ea8f  call    cs:__guard_dispatch_icall_fptr
0x10041ea95  jmp     short loc_10041EA9F
0x10041ea97  mov     esi, [rsp+0D8h+var_A4]
0x10041ea9b  mov     [rsp+0D8h+var_A8], esi
0x10041ea9f  mov     rcx, [rsp+0D8h+arg_8]
0x10041eaa7  test    rcx, rcx
0x10041eaaa  jz      short loc_10041EAB9
0x10041eaac  mov     rax, [rcx]
0x10041eaaf  mov     rax, [rax+10h]
0x10041eab3  call    cs:__guard_dispatch_icall_fptr
0x10041eab9  mov     eax, esi
0x10041eabb  lea     r11, [rsp+0D8h+var_8]
0x10041eac3  mov     rbx, [r11+10h]
0x10041eac7  mov     rsi, [r11+20h]
0x10041eacb  mov     rdi, [r11+28h]
0x10041eacf  mov     rsp, r11
0x10041ead2  pop     r14
0x10041ead4  retn
0x10041ead5  mov     ecx, 80070057h; int
0x10041eada  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10041eadf  mov     ecx, 80070057h; int
0x10041eae4  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10041eae9  nop
0x10041eaea  int     3; Trap to Debugger
0x10043a540  push    rbp
0x10043a542  sub     rsp, 30h
0x10043a546  mov     rbp, rdx
0x10043a549  mov     [rbp+0C0h], rcx
0x10043a550  mov     [rbp+70h], rcx
0x10043a554  mov     rax, [rbp+70h]
0x10043a558  mov     rcx, [rax]
0x10043a55b  mov     [rbp+40h], rcx
0x10043a55f  mov     rax, [rbp+40h]
0x10043a563  mov     eax, [rax]
0x10043a565  cmp     eax, 0C0000005h
0x10043a56a  jz      short loc_10043A59C
0x10043a56c  add     eax, 1FFFFFFFh
0x10043a571  cmp     eax, 1
0x10043a574  ja      short loc_10043A58C
0x10043a576  mov     rax, [rbp+40h]
0x10043a57a  cmp     dword ptr [rax+18h], 1
0x10043a57e  jnz     short loc_10043A58C
0x10043a580  mov     rax, [rbp+40h]
0x10043a584  mov     ecx, [rax+20h]
0x10043a587  mov     [rbp+34h], ecx
0x10043a58a  jmp     short loc_10043A593
0x10043a58c  mov     dword ptr [rbp+34h], 8000FFFFh
0x10043a593  mov     dword ptr [rbp+38h], 1
0x10043a59a  jmp     short loc_10043A5A3
0x10043a59c  mov     dword ptr [rbp+38h], 0
0x10043a5a3  mov     eax, [rbp+38h]
0x10043a5a6  add     rsp, 30h
0x10043a5aa  pop     rbp
0x10043a5ab  retn
```
