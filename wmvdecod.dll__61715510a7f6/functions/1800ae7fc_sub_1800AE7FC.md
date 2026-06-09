# sub_1800AE7FC

- ea: `0x1800ae7fc`
- end: `0x1800ae968`
- name: `sub_1800AE7FC`
- size: `364`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180092664`
- `0x1800b3e64`

## callees

- `0x1800013a8`
- `0x1800019b0`
- `0x18008c580`
- `0x1800994a0`
- `0x1800ae7fc`
- `0x18020cab0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800ae92e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800ae92e`

## string_xrefs

- `0x1800ae825`: `m_pDXVA2DecoderService == NULL`

## pseudocode

```c
__int64 __fastcall sub_1800AE7FC(__int64 *a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v5; // rcx
  __int64 v9; // rcx
  __int64 v10; // r8
  GUID *v11; // rax
  __int64 v12; // rcx
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  int v17; // [rsp+50h] [rbp-21h] BYREF
  int v18; // [rsp+54h] [rbp-1Dh] BYREF
  __int64 v19; // [rsp+58h] [rbp-19h] BYREF
  GUID *v20; // [rsp+60h] [rbp-11h] BYREF
  const wchar_t *v21; // [rsp+68h] [rbp-9h] BYREF
  _QWORD v22[2]; // [rsp+70h] [rbp-1h] BYREF
  GUID v23; // [rsp+80h] [rbp+Fh] BYREF

  v5 = *a1;
  if ( !v5 || !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 320LL))(v5, qword_18021C578) )
  {
    v9 = *a1;
    v10 = 0;
    v23 = Buf2;
    if ( v9 )
    {
      v11 = (GUID *)(*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v9 + 280LL))(v9, v22, 0);
      v12 = *a1;
      v23 = *v11;
      v10 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v12 + 296LL))(v12);
    }
    if ( (unsigned int)dword_180281118 > 5 && (unsigned __int8)sub_1800019B0(v9, 0x200000000000LL, v10) )
    {
      v19 = a2;
      v20 = &v23;
      v17 = v14;
      v21 = L"m_pDXVA2DecoderService == NULL";
      v18 = a4;
      v22[0] = a3;
      sub_1800013A8(
        v13,
        (unsigned int)&dword_18027728C,
        v14,
        v15,
        (__int64)v22,
        (__int64)&v18,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v17,
        (__int64)&v19);
    }
  }
  if ( a4 < 0 )
    RoOriginateErrorW((unsigned int)a4, 30, L"m_pDXVA2DecoderService == NULL");
  sub_18008C580(a1);
  return (unsigned int)a4;
}

```

## disassembly

```asm
0x1800ae7fc  mov     [rsp-8+arg_8], rbx
0x1800ae801  push    rbp
0x1800ae802  push    rsi
0x1800ae803  push    rdi
0x1800ae804  push    r14
0x1800ae806  push    r15
0x1800ae808  lea     rbp, [rsp-2Fh]
0x1800ae80d  sub     rsp, 0A0h
0x1800ae814  mov     rax, cs:__security_cookie
0x1800ae81b  xor     rax, rsp
0x1800ae81e  mov     [rbp+4Fh+var_30], rax
0x1800ae822  mov     rdi, rcx
0x1800ae825  lea     r15, aMPdxva2decoder; "m_pDXVA2DecoderService == NULL"
0x1800ae82c  mov     rcx, [rcx]
0x1800ae82f  mov     ebx, r9d
0x1800ae832  mov     rsi, r8
0x1800ae835  mov     r14, rdx
0x1800ae838  test    rcx, rcx
0x1800ae83b  jz      short loc_1800AE85C
0x1800ae83d  mov     rax, [rcx]
0x1800ae840  lea     rdx, qword_18021C578
0x1800ae847  mov     rax, [rax+140h]
0x1800ae84e  call    cs:__guard_dispatch_icall_fptr
0x1800ae854  test    eax, eax
0x1800ae856  jnz     loc_1800AE920
0x1800ae85c  movups  xmm0, xmmword ptr cs:Buf2.Data1
0x1800ae863  mov     rcx, [rdi]
0x1800ae866  xor     r8d, r8d
0x1800ae869  movdqu  [rbp+4Fh+var_40], xmm0
0x1800ae86e  test    rcx, rcx
0x1800ae871  jz      short loc_1800AE8A5
0x1800ae873  mov     rax, [rcx]
0x1800ae876  lea     rdx, [rbp+4Fh+var_50]
0x1800ae87a  mov     rax, [rax+118h]
0x1800ae881  call    cs:__guard_dispatch_icall_fptr
0x1800ae887  mov     rcx, [rdi]
0x1800ae88a  movups  xmm0, xmmword ptr [rax]
0x1800ae88d  movdqu  [rbp+4Fh+var_40], xmm0
0x1800ae892  mov     rax, [rcx]
0x1800ae895  mov     rax, [rax+128h]
0x1800ae89c  call    cs:__guard_dispatch_icall_fptr
0x1800ae8a2  mov     r8d, eax
0x1800ae8a5  mov     eax, cs:dword_180281118
0x1800ae8ab  cmp     eax, 5
0x1800ae8ae  jbe     short loc_1800AE920
0x1800ae8b0  mov     rdx, 200000000000h
0x1800ae8ba  call    sub_1800019B0
0x1800ae8bf  test    al, al
0x1800ae8c1  jz      short loc_1800AE920
0x1800ae8c3  lea     rax, [rbp+4Fh+var_40]
0x1800ae8c7  mov     [rbp+4Fh+var_68], r14
0x1800ae8cb  mov     [rbp+4Fh+var_60], rax
0x1800ae8cf  lea     rdx, dword_18027728C
0x1800ae8d6  lea     rax, [rbp+4Fh+var_68]
0x1800ae8da  mov     [rbp+4Fh+var_70], r8d
0x1800ae8de  mov     [rsp+0C0h+var_78], rax
0x1800ae8e3  lea     rax, [rbp+4Fh+var_70]
0x1800ae8e7  mov     [rsp+0C0h+var_80], rax
0x1800ae8ec  lea     rax, [rbp+4Fh+var_60]
0x1800ae8f0  mov     [rsp+0C0h+var_88], rax
0x1800ae8f5  lea     rax, [rbp+4Fh+var_58]
0x1800ae8f9  mov     [rsp+0C0h+var_90], rax
0x1800ae8fe  lea     rax, [rbp+4Fh+var_6C]
0x1800ae902  mov     [rsp+0C0h+var_98], rax
0x1800ae907  lea     rax, [rbp+4Fh+var_50]
0x1800ae90b  mov     [rsp+0C0h+var_A0], rax
0x1800ae910  mov     [rbp+4Fh+var_58], r15
0x1800ae914  mov     [rbp+4Fh+var_6C], ebx
0x1800ae917  mov     [rbp+4Fh+var_50], rsi
0x1800ae91b  call    sub_1800013A8
0x1800ae920  test    ebx, ebx
0x1800ae922  jns     short loc_1800AE93A
0x1800ae924  mov     r8, r15
0x1800ae927  mov     edx, 1Eh
0x1800ae92c  mov     ecx, ebx
0x1800ae92e  call    cs:RoOriginateErrorW
0x1800ae935  nop     dword ptr [rax+rax+00h]
0x1800ae93a  mov     rcx, rdi
0x1800ae93d  call    sub_18008C580
0x1800ae942  mov     eax, ebx
0x1800ae944  mov     rcx, [rbp+4Fh+var_30]
0x1800ae948  xor     rcx, rsp; StackCookie
0x1800ae94b  call    __security_check_cookie
0x1800ae950  mov     rbx, [rsp+0C0h+arg_8]
0x1800ae958  add     rsp, 0A0h
0x1800ae95f  pop     r15
0x1800ae961  pop     r14
0x1800ae963  pop     rdi
0x1800ae964  pop     rsi
0x1800ae965  pop     rbp
0x1800ae966  retn
```
