# sub_14012BDFC

- ea: `0x14012bdfc`
- end: `0x14012c10b`
- name: `sub_14012BDFC`
- size: `783`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14012bb04`

## callees

- `0x140059870`
- `0x14006ad34`
- `0x14006c298`
- `0x14006de60`
- `0x14007cfb4`
- `0x14012bdfc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14012be8f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14012bebb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14012be8f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14012bebb`
- `OLEAUT32!VariantInit` at `0x14012be51`
- `OLEAUT32!VariantInit` at `0x14012be68`
- `OLEAUT32!VariantInit` at `0x14012be51`
- `OLEAUT32!VariantInit` at `0x14012be68`
- `OLEAUT32!VariantClear` at `0x14012c0c2`
- `OLEAUT32!VariantClear` at `0x14012c0c2`

## string_xrefs

- `0x14012bfa1`: `http://xml.org/sax/properties/lexical-handler`

## pseudocode

```c
__int64 __fastcall sub_14012BDFC(LONGLONG a1, __int64 a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, void *, __int64 *); // rbx
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, __int64); // rbx
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, void *, LONGLONG *); // rbx
  LPVOID v12; // rdi
  __int64 v13; // rax
  __int64 (__fastcall *v14)(LPVOID, const wchar_t *, VARIANTARG *); // rbx
  LPVOID v15; // rdi
  __int64 (__fastcall *v16)(LPVOID, __int64); // rbx
  LPVOID v17; // rdi
  __int64 (__fastcall *v18)(LPVOID, __int64); // rbx
  LPVOID v19; // rdi
  __int64 v20; // rax
  __int64 (__fastcall *v21)(LPVOID, VARIANTARG *); // rbx
  LPVOID v22; // rdi
  __int64 (__fastcall *v23)(LPVOID, VARIANTARG *); // rbx
  int v24; // ecx
  LONGLONG v26; // [rsp+30h] [rbp-29h] BYREF
  __int64 v27; // [rsp+38h] [rbp-21h] BYREF
  VARIANTARG v28; // [rsp+40h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-1h] BYREF
  VARIANTARG v30; // [rsp+70h] [rbp+17h] BYREF
  LPVOID v31; // [rsp+D0h] [rbp+77h] BYREF
  LPVOID ppv; // [rsp+D8h] [rbp+7Fh] BYREF

  ppv = 0;
  v31 = 0;
  v27 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v26 = 0;
  VariantInit(&pvarg);
  memset(&v28, 0, sizeof(v28));
  VariantInit(&v28);
  v4 = CoCreateInstance(&stru_1403C0B30, 0, 1u, &stru_1403CC9D0, &ppv);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_14;
  v4 = CoCreateInstance(&stru_1403C0B40, 0, 1u, &stru_1403CC9C0, &v31);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_14;
  v6 = v31;
  v7 = **(__int64 (__fastcall ***)(LPVOID, void *, __int64 *))v31;
  _guard_check_icall_fptr();
  v4 = v7(v6, &unk_1403CC9B0, &v27);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_14;
  v8 = ppv;
  v9 = *(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 80LL);
  _guard_check_icall_fptr();
  v4 = v9(v8, v27);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_14;
  v10 = v31;
  v11 = **(__int64 (__fastcall ***)(LPVOID, void *, LONGLONG *))v31;
  _guard_check_icall_fptr();
  v4 = v11(v10, &unk_1403CC9A0, &v26);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_14;
  v12 = ppv;
  v28.llVal = v26;
  v28.vt = 13;
  v13 = *(_QWORD *)ppv;
  v30 = v28;
  v14 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v13 + 48);
  _guard_check_icall_fptr();
  v4 = v14(v12, L"http://xml.org/sax/properties/lexical-handler", &v30);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_14;
  v15 = v31;
  v16 = *(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v31 + 104LL);
  _guard_check_icall_fptr();
  v4 = v16(v15, 0xFFFF);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_14;
  v17 = v31;
  v18 = *(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v31 + 136LL);
  _guard_check_icall_fptr();
  v4 = v18(v17, 0xFFFF);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_14;
  v19 = ppv;
  v28.vt = 13;
  v28.llVal = a1;
  v20 = *(_QWORD *)ppv;
  v30 = v28;
  v21 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *))(v20 + 152);
  _guard_check_icall_fptr();
  v4 = v21(v19, &v30);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_14;
  v22 = v31;
  v23 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *))(*(_QWORD *)v31 + 64LL);
  _guard_check_icall_fptr();
  v4 = v23(v22, &pvarg);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_14;
  if ( pvarg.vt != 8 )
  {
    v5 = -2147467259;
    v24 = -2147467259;
LABEL_15:
    sub_14006DE60(v24);
    goto LABEL_16;
  }
  v4 = sub_14006C298(pvarg.llVal, a2, 0x7FFFFFFF);
  v5 = v4;
  if ( v4 < 0 )
  {
LABEL_14:
    v24 = v4;
    goto LABEL_15;
  }
LABEL_16:
  sub_14007CFB4(v5);
  VariantClear(&pvarg);
  sub_14006AD34(&v26);
  sub_14006AD34(&v27);
  sub_14006AD34((__int64 *)&v31);
  sub_14006AD34((__int64 *)&ppv);
  return v5;
}

```

## disassembly

```asm
0x14012bdfc  mov     [rsp-8+arg_0], rbx
0x14012be01  mov     [rsp-8+arg_8], rsi
0x14012be06  push    rbp
0x14012be07  push    rdi
0x14012be08  push    r12
0x14012be0a  push    r13
0x14012be0c  push    r14
0x14012be0e  lea     rbp, [rsp-37h]
0x14012be13  sub     rsp, 90h
0x14012be1a  mov     r14, rcx
0x14012be1d  mov     [rbp+57h+arg_18], 0
0x14012be25  xorps   xmm0, xmm0
0x14012be28  mov     [rbp+57h+arg_10], 0
0x14012be30  xor     eax, eax
0x14012be32  mov     [rbp+57h+var_78], 0
0x14012be3a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14012be3e  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x14012be42  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x14012be46  mov     rsi, rdx
0x14012be49  mov     [rbp+57h+var_80], 0
0x14012be51  call    cs:VariantInit
0x14012be57  xorps   xmm0, xmm0
0x14012be5a  lea     rcx, [rbp+57h+var_70]; pvarg
0x14012be5e  xor     eax, eax
0x14012be60  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x14012be64  mov     qword ptr [rbp+57h+var_70+10h], rax
0x14012be68  call    cs:VariantInit
0x14012be6e  lea     rax, [rbp+57h+arg_18]
0x14012be72  mov     edi, 1
0x14012be77  mov     r8d, edi; dwClsContext
0x14012be7a  mov     [rsp+0B0h+ppv], rax; ppv
0x14012be7f  lea     r9, stru_1403CC9D0; riid
0x14012be86  xor     edx, edx; pUnkOuter
0x14012be88  lea     rcx, stru_1403C0B30; rclsid
0x14012be8f  call    cs:CoCreateInstance
0x14012be95  mov     ebx, eax
0x14012be97  test    eax, eax
0x14012be99  js      loc_14012C0B0
0x14012be9f  lea     rax, [rbp+57h+arg_10]
0x14012bea3  mov     r8d, edi; dwClsContext
0x14012bea6  lea     r9, stru_1403CC9C0; riid
0x14012bead  mov     [rsp+0B0h+ppv], rax; ppv
0x14012beb2  xor     edx, edx; pUnkOuter
0x14012beb4  lea     rcx, stru_1403C0B40; rclsid
0x14012bebb  call    cs:CoCreateInstance
0x14012bec1  mov     ebx, eax
0x14012bec3  test    eax, eax
0x14012bec5  js      loc_14012C0B0
0x14012becb  mov     rdi, [rbp+57h+arg_10]
0x14012becf  mov     rax, [rdi]
0x14012bed2  mov     rbx, [rax]
0x14012bed5  mov     rax, cs:__guard_check_icall_fptr
0x14012bedc  mov     rcx, rbx
0x14012bedf  call    rax ; _guard_check_icall_nop
0x14012bee1  mov     rax, rbx
0x14012bee4  lea     r8, [rbp+57h+var_78]
0x14012bee8  lea     rdx, unk_1403CC9B0
0x14012beef  mov     rcx, rdi
0x14012bef2  call    rax
0x14012bef4  mov     ebx, eax
0x14012bef6  test    eax, eax
0x14012bef8  js      loc_14012C0B0
0x14012befe  mov     rdi, [rbp+57h+arg_18]
0x14012bf02  mov     rax, [rdi]
0x14012bf05  mov     rbx, [rax+50h]
0x14012bf09  mov     rax, cs:__guard_check_icall_fptr
0x14012bf10  mov     rcx, rbx
0x14012bf13  call    rax ; _guard_check_icall_nop
0x14012bf15  mov     rdx, [rbp+57h+var_78]
0x14012bf19  mov     rax, rbx
0x14012bf1c  mov     rcx, rdi
0x14012bf1f  call    rax
0x14012bf21  mov     ebx, eax
0x14012bf23  test    eax, eax
0x14012bf25  js      loc_14012C0B0
0x14012bf2b  mov     rdi, [rbp+57h+arg_10]
0x14012bf2f  mov     rax, [rdi]
0x14012bf32  mov     rbx, [rax]
0x14012bf35  mov     rax, cs:__guard_check_icall_fptr
0x14012bf3c  mov     rcx, rbx
0x14012bf3f  call    rax ; _guard_check_icall_nop
0x14012bf41  mov     rax, rbx
0x14012bf44  lea     r8, [rbp+57h+var_80]
0x14012bf48  lea     rdx, unk_1403CC9A0
0x14012bf4f  mov     rcx, rdi
0x14012bf52  call    rax
0x14012bf54  mov     ebx, eax
0x14012bf56  test    eax, eax
0x14012bf58  js      loc_14012C0B0
0x14012bf5e  mov     rax, [rbp+57h+var_80]
0x14012bf62  mov     r13d, 0Dh
0x14012bf68  movsd   xmm1, qword ptr [rbp+57h+var_70+10h]
0x14012bf6d  mov     rdi, [rbp+57h+arg_18]
0x14012bf71  mov     qword ptr [rbp+57h+var_70+8], rax
0x14012bf75  mov     word ptr [rbp+57h+var_70], r13w
0x14012bf7a  movups  xmm0, xmmword ptr [rbp+57h+var_70]
0x14012bf7e  mov     rax, [rdi]
0x14012bf81  movsd   [rbp+57h+var_30], xmm1
0x14012bf86  movaps  [rbp+57h+var_40], xmm0
0x14012bf8a  mov     rbx, [rax+30h]
0x14012bf8e  mov     rax, cs:__guard_check_icall_fptr
0x14012bf95  mov     rcx, rbx
0x14012bf98  call    rax ; _guard_check_icall_nop
0x14012bf9a  mov     rax, rbx
0x14012bf9d  lea     r8, [rbp+57h+var_40]
0x14012bfa1  lea     rdx, aHttpXmlOrgSaxP; "http://xml.org/sax/properties/lexical-h"...
0x14012bfa8  mov     rcx, rdi
0x14012bfab  call    rax
0x14012bfad  mov     ebx, eax
0x14012bfaf  test    eax, eax
0x14012bfb1  js      loc_14012C0B0
0x14012bfb7  mov     rdi, [rbp+57h+arg_10]
0x14012bfbb  or      r12d, 0FFFFFFFFh
0x14012bfbf  mov     rax, [rdi]
0x14012bfc2  mov     rbx, [rax+68h]
0x14012bfc6  mov     rax, cs:__guard_check_icall_fptr
0x14012bfcd  mov     rcx, rbx
0x14012bfd0  call    rax ; _guard_check_icall_nop
0x14012bfd2  mov     rax, rbx
0x14012bfd5  movzx   edx, r12w
0x14012bfd9  mov     rcx, rdi
0x14012bfdc  call    rax
0x14012bfde  mov     ebx, eax
0x14012bfe0  test    eax, eax
0x14012bfe2  js      loc_14012C0B0
0x14012bfe8  mov     rdi, [rbp+57h+arg_10]
0x14012bfec  mov     rax, [rdi]
0x14012bfef  mov     rbx, [rax+88h]
0x14012bff6  mov     rax, cs:__guard_check_icall_fptr
0x14012bffd  mov     rcx, rbx
0x14012c000  call    rax ; _guard_check_icall_nop
0x14012c002  mov     rax, rbx
0x14012c005  movzx   edx, r12w
0x14012c009  mov     rcx, rdi
0x14012c00c  call    rax
0x14012c00e  mov     ebx, eax
0x14012c010  test    eax, eax
0x14012c012  js      loc_14012C0B0
0x14012c018  movsd   xmm1, qword ptr [rbp+57h+var_70+10h]
0x14012c01d  mov     rdi, [rbp+57h+arg_18]
0x14012c021  mov     word ptr [rbp+57h+var_70], r13w
0x14012c026  mov     qword ptr [rbp+57h+var_70+8], r14
0x14012c02a  movups  xmm0, xmmword ptr [rbp+57h+var_70]
0x14012c02e  mov     rax, [rdi]
0x14012c031  movsd   [rbp+57h+var_30], xmm1
0x14012c036  movaps  [rbp+57h+var_40], xmm0
0x14012c03a  mov     rbx, [rax+98h]
0x14012c041  mov     rax, cs:__guard_check_icall_fptr
0x14012c048  mov     rcx, rbx
0x14012c04b  call    rax ; _guard_check_icall_nop
0x14012c04d  mov     rax, rbx
0x14012c050  lea     rdx, [rbp+57h+var_40]
0x14012c054  mov     rcx, rdi
0x14012c057  call    rax
0x14012c059  mov     ebx, eax
0x14012c05b  test    eax, eax
0x14012c05d  js      short loc_14012C0B0
0x14012c05f  mov     rdi, [rbp+57h+arg_10]
0x14012c063  mov     rax, [rdi]
0x14012c066  mov     rbx, [rax+40h]
0x14012c06a  mov     rax, cs:__guard_check_icall_fptr
0x14012c071  mov     rcx, rbx
0x14012c074  call    rax ; _guard_check_icall_nop
0x14012c076  mov     rax, rbx
0x14012c079  lea     rdx, [rbp+57h+pvarg]
0x14012c07d  mov     rcx, rdi
0x14012c080  call    rax
0x14012c082  mov     ebx, eax
0x14012c084  test    eax, eax
0x14012c086  js      short loc_14012C0B0
0x14012c088  cmp     word ptr [rbp+57h+pvarg], 8
0x14012c08d  jz      short loc_14012C098
0x14012c08f  mov     ebx, 80004005h
0x14012c094  mov     ecx, ebx
0x14012c096  jmp     short loc_14012C0B2
0x14012c098  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x14012c09c  mov     r8d, 7FFFFFFFh
0x14012c0a2  mov     rdx, rsi
0x14012c0a5  call    sub_14006C298
0x14012c0aa  mov     ebx, eax
0x14012c0ac  test    eax, eax
0x14012c0ae  jns     short loc_14012C0B7
0x14012c0b0  mov     ecx, eax
0x14012c0b2  call    sub_14006DE60
0x14012c0b7  mov     ecx, ebx
0x14012c0b9  call    sub_14007CFB4
0x14012c0be  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14012c0c2  call    cs:VariantClear
0x14012c0c8  lea     rcx, [rbp+57h+var_80]
0x14012c0cc  call    sub_14006AD34
0x14012c0d1  lea     rcx, [rbp+57h+var_78]
0x14012c0d5  call    sub_14006AD34
0x14012c0da  lea     rcx, [rbp+57h+arg_10]
0x14012c0de  call    sub_14006AD34
0x14012c0e3  lea     rcx, [rbp+57h+arg_18]
0x14012c0e7  call    sub_14006AD34
0x14012c0ec  lea     r11, [rsp+0B0h+var_20]
0x14012c0f4  mov     eax, ebx
0x14012c0f6  mov     rbx, [r11+30h]
0x14012c0fa  mov     rsi, [r11+38h]
0x14012c0fe  mov     rsp, r11
0x14012c101  pop     r14
0x14012c103  pop     r13
0x14012c105  pop     r12
0x14012c107  pop     rdi
0x14012c108  pop     rbp
0x14012c109  retn
```
