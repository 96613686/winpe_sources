# VbsErase(VAR *,int,VAR *)

- ea: `0x180071af0`
- end: `0x180071c52`
- name: `?VbsErase@@YAJPEAVVAR@@H0@Z`
- size: `354`
- prototype: `__int64 __fastcall(struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180040cc4`
- `0x180071af0`
- `0x18007552c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x180071bee`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x180071bee`
- `OLEAUT32!__imp_SafeArrayDestroyData` at `0x180071b92`
- `OLEAUT32!__imp_SafeArrayDestroyData` at `0x180071b92`

## pseudocode

```c
HRESULT __fastcall VbsErase(struct VAR *a1, int a2, struct VAR *a3)
{
  HRESULT result; // eax
  __int16 *v4; // rbx
  __int16 v5; // cx
  __int64 *v6; // rsi
  __int64 **v7; // r14
  HRESULT v8; // edi
  int v9; // r12d
  const unsigned __int16 *v10; // r8
  int v11; // r9d
  __int16 v12; // [rsp+20h] [rbp-28h]
  int v13; // [rsp+22h] [rbp-26h]
  __int16 v14; // [rsp+26h] [rbp-22h]
  __int64 *v15; // [rsp+28h] [rbp-20h] BYREF
  __int64 v16; // [rsp+30h] [rbp-18h]

  if ( a2 != 1 )
    return -2146827838;
  if ( *(_WORD *)a3 != 16396 )
    return -2146828275;
  v4 = (__int16 *)*((_QWORD *)a3 + 1);
  v5 = *v4;
  v6 = (__int64 *)*((_QWORD *)v4 + 1);
  v13 = *(_DWORD *)(v4 + 1);
  v14 = v4[3];
  v16 = *((_QWORD *)v4 + 2);
  v12 = v5;
  v15 = v6;
  if ( v5 == 8204 )
  {
    v7 = &v15;
    goto LABEL_8;
  }
  if ( v5 != 24588 )
    return -2146828275;
  v7 = (__int64 **)v6;
  v6 = (__int64 *)*v6;
LABEL_8:
  v8 = 0;
  if ( !v6 )
    return v8;
  *v7 = 0;
  v9 = 0;
  if ( v5 == 8204 )
    *v4 = 0;
  v8 = SafeArrayDestroyData((SAFEARRAY *)v6);
  if ( v12 == 8204 )
  {
    if ( *v4 )
      v9 = 1;
    else
      *v4 = 8204;
  }
  else if ( v12 == 24588 && *v4 != 24588 )
  {
    VBScriptClass_Report_Unexpected_Fatal_Error(v4);
  }
  *v7 = v6;
  if ( v8 < 0 )
    return v8;
  if ( (*((_BYTE *)v6 + 2) & 7) != 0 )
  {
LABEL_23:
    if ( v9 == 1 )
      RaiseErrorHr(-2147418113, (struct VAR *)v4, v10, v11);
    if ( v12 == 8204 )
    {
      *(_DWORD *)(v4 + 1) = v13;
      v4[3] = v14;
      *((_QWORD *)v4 + 1) = v15;
      *((_QWORD *)v4 + 2) = v16;
      *v4 = 8204;
    }
    return v8;
  }
  result = SafeArrayDestroyDescriptor((SAFEARRAY *)v6);
  v8 = result;
  if ( result >= 0 )
  {
    *v7 = 0;
    goto LABEL_23;
  }
  return result;
}

```

## disassembly

```asm
0x180071af0  push    rbp
0x180071af2  push    rbx
0x180071af3  push    rsi
0x180071af4  push    rdi
0x180071af5  push    r12
0x180071af7  push    r13
0x180071af9  push    r14
0x180071afb  push    r15
0x180071afd  mov     rbp, rsp
0x180071b00  sub     rsp, 48h
0x180071b04  cmp     edx, 1
0x180071b07  jz      short loc_180071B13
0x180071b09  mov     eax, 800A01C2h
0x180071b0e  jmp     loc_180071C41
0x180071b13  mov     eax, 400Ch
0x180071b18  cmp     ax, [r8]
0x180071b1c  jnz     loc_180071C3C
0x180071b22  mov     rbx, [r8+8]
0x180071b26  mov     edx, 600Ch
0x180071b2b  mov     eax, [rbx+2]
0x180071b2e  movzx   ecx, word ptr [rbx]
0x180071b31  mov     rsi, [rbx+8]
0x180071b35  mov     [rbp+var_26], eax
0x180071b38  movzx   eax, word ptr [rbx+6]
0x180071b3c  mov     [rbp+var_22], ax
0x180071b40  mov     rax, [rbx+10h]
0x180071b44  mov     [rbp+var_18], rax
0x180071b48  mov     eax, 200Ch
0x180071b4d  mov     [rbp+var_28], cx
0x180071b51  mov     [rbp+var_20], rsi
0x180071b55  cmp     ax, cx
0x180071b58  jnz     short loc_180071B60
0x180071b5a  lea     r14, [rbp+var_20]
0x180071b5e  jmp     short loc_180071B6F
0x180071b60  cmp     dx, cx
0x180071b63  jnz     loc_180071C3C
0x180071b69  mov     r14, rsi
0x180071b6c  mov     rsi, [rsi]
0x180071b6f  xor     r13d, r13d
0x180071b72  mov     edi, r13d
0x180071b75  test    rsi, rsi
0x180071b78  jz      short loc_180071BE1
0x180071b7a  mov     [r14], r13
0x180071b7d  mov     r12d, r13d
0x180071b80  movzx   r15d, [rbp+var_28]
0x180071b85  cmp     ax, r15w
0x180071b89  jnz     short loc_180071B8F
0x180071b8b  mov     [rbx], r13w
0x180071b8f  mov     rcx, rsi; psa
0x180071b92  call    cs:__imp_SafeArrayDestroyData
0x180071b98  mov     edi, eax
0x180071b9a  mov     eax, 200Ch
0x180071b9f  cmp     ax, r15w
0x180071ba3  jnz     short loc_180071BBC
0x180071ba5  mov     r15d, eax
0x180071ba8  cmp     [rbx], r13w
0x180071bac  jz      short loc_180071BB6
0x180071bae  mov     r12d, 1
0x180071bb4  jmp     short loc_180071BDA
0x180071bb6  mov     [rbx], r15w
0x180071bba  jmp     short loc_180071BDA
0x180071bbc  mov     eax, 600Ch
0x180071bc1  cmp     ax, r15w
0x180071bc5  jnz     short loc_180071BD4
0x180071bc7  cmp     [rbx], ax
0x180071bca  jz      short loc_180071BD4
0x180071bcc  mov     rcx, rbx
0x180071bcf  call    VBScriptClass_Report_Unexpected_Fatal_Error
0x180071bd4  mov     r15d, 200Ch
0x180071bda  mov     [r14], rsi
0x180071bdd  test    edi, edi
0x180071bdf  jns     short loc_180071BE5
0x180071be1  mov     eax, edi
0x180071be3  jmp     short loc_180071C41
0x180071be5  test    byte ptr [rsi+2], 7
0x180071be9  jnz     short loc_180071BFD
0x180071beb  mov     rcx, rsi; psa
0x180071bee  call    cs:__imp_SafeArrayDestroyDescriptor
0x180071bf4  mov     edi, eax
0x180071bf6  test    eax, eax
0x180071bf8  js      short loc_180071C41
0x180071bfa  mov     [r14], r13
0x180071bfd  cmp     r12d, 1
0x180071c01  jnz     short loc_180071C11
0x180071c03  mov     rdx, rbx; struct VAR *
0x180071c06  mov     ecx, 8000FFFFh; int
0x180071c0b  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x180071c11  cmp     r15w, [rbp+var_28]
0x180071c16  jnz     short loc_180071BE1
0x180071c18  mov     eax, [rbp+var_26]
0x180071c1b  mov     [rbx+2], eax
0x180071c1e  movzx   eax, [rbp+var_22]
0x180071c22  mov     [rbx+6], ax
0x180071c26  mov     rax, [rbp+var_20]
0x180071c2a  mov     [rbx+8], rax
0x180071c2e  mov     rax, [rbp+var_18]
0x180071c32  mov     [rbx+10h], rax
0x180071c36  mov     [rbx], r15w
0x180071c3a  jmp     short loc_180071BE1
0x180071c3c  mov     eax, 800A000Dh
0x180071c41  add     rsp, 48h
0x180071c45  pop     r15
0x180071c47  pop     r14
0x180071c49  pop     r13
0x180071c4b  pop     r12
0x180071c4d  pop     rdi
0x180071c4e  pop     rsi
0x180071c4f  pop     rbx
0x180071c50  pop     rbp
0x180071c51  retn
```
