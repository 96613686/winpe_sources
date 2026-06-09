# VbsErase(VAR *,int,VAR *)

- ea: `0x180074030`
- end: `0x18007419f`
- name: `?VbsErase@@YAJPEAVVAR@@H0@Z`
- size: `367`
- prototype: `HRESULT __fastcall(struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18004237c`
- `0x180074030`
- `0x180078100`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x180074134`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x180074134`
- `OLEAUT32!__imp_SafeArrayDestroyData` at `0x1800740d2`
- `OLEAUT32!__imp_SafeArrayDestroyData` at `0x1800740d2`

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
0x180074030  push    rbp
0x180074032  push    rbx
0x180074033  push    rsi
0x180074034  push    rdi
0x180074035  push    r12
0x180074037  push    r13
0x180074039  push    r14
0x18007403b  push    r15
0x18007403d  mov     rbp, rsp
0x180074040  sub     rsp, 48h
0x180074044  cmp     edx, 1
0x180074047  jz      short loc_180074053
0x180074049  mov     eax, 800A01C2h
0x18007404e  jmp     loc_18007418D
0x180074053  mov     eax, 400Ch
0x180074058  cmp     ax, [r8]
0x18007405c  jnz     loc_180074188
0x180074062  mov     rbx, [r8+8]
0x180074066  mov     edx, 600Ch
0x18007406b  mov     eax, [rbx+2]
0x18007406e  movzx   ecx, word ptr [rbx]
0x180074071  mov     rsi, [rbx+8]
0x180074075  mov     [rbp+var_26], eax
0x180074078  movzx   eax, word ptr [rbx+6]
0x18007407c  mov     [rbp+var_22], ax
0x180074080  mov     rax, [rbx+10h]
0x180074084  mov     [rbp+var_18], rax
0x180074088  mov     eax, 200Ch
0x18007408d  mov     [rbp+var_28], cx
0x180074091  mov     [rbp+var_20], rsi
0x180074095  cmp     ax, cx
0x180074098  jnz     short loc_1800740A0
0x18007409a  lea     r14, [rbp+var_20]
0x18007409e  jmp     short loc_1800740AF
0x1800740a0  cmp     dx, cx
0x1800740a3  jnz     loc_180074188
0x1800740a9  mov     r14, rsi
0x1800740ac  mov     rsi, [rsi]
0x1800740af  xor     r13d, r13d
0x1800740b2  mov     edi, r13d
0x1800740b5  test    rsi, rsi
0x1800740b8  jz      short loc_180074127
0x1800740ba  mov     [r14], r13
0x1800740bd  mov     r12d, r13d
0x1800740c0  movzx   r15d, [rbp+var_28]
0x1800740c5  cmp     ax, r15w
0x1800740c9  jnz     short loc_1800740CF
0x1800740cb  mov     [rbx], r13w
0x1800740cf  mov     rcx, rsi; psa
0x1800740d2  call    cs:__imp_SafeArrayDestroyData
0x1800740d9  nop     dword ptr [rax+rax+00h]
0x1800740de  mov     edi, eax
0x1800740e0  mov     eax, 200Ch
0x1800740e5  cmp     ax, r15w
0x1800740e9  jnz     short loc_180074102
0x1800740eb  mov     r15d, eax
0x1800740ee  cmp     [rbx], r13w
0x1800740f2  jz      short loc_1800740FC
0x1800740f4  mov     r12d, 1
0x1800740fa  jmp     short loc_180074120
0x1800740fc  mov     [rbx], r15w
0x180074100  jmp     short loc_180074120
0x180074102  mov     eax, 600Ch
0x180074107  cmp     ax, r15w
0x18007410b  jnz     short loc_18007411A
0x18007410d  cmp     [rbx], ax
0x180074110  jz      short loc_18007411A
0x180074112  mov     rcx, rbx
0x180074115  call    VBScriptClass_Report_Unexpected_Fatal_Error
0x18007411a  mov     r15d, 200Ch
0x180074120  mov     [r14], rsi
0x180074123  test    edi, edi
0x180074125  jns     short loc_18007412B
0x180074127  mov     eax, edi
0x180074129  jmp     short loc_18007418D
0x18007412b  test    byte ptr [rsi+2], 7
0x18007412f  jnz     short loc_180074149
0x180074131  mov     rcx, rsi; psa
0x180074134  call    cs:__imp_SafeArrayDestroyDescriptor
0x18007413b  nop     dword ptr [rax+rax+00h]
0x180074140  mov     edi, eax
0x180074142  test    eax, eax
0x180074144  js      short loc_18007418D
0x180074146  mov     [r14], r13
0x180074149  cmp     r12d, 1
0x18007414d  jnz     short loc_18007415D
0x18007414f  mov     rdx, rbx; struct VAR *
0x180074152  mov     ecx, 8000FFFFh; int
0x180074157  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x18007415d  cmp     r15w, [rbp+var_28]
0x180074162  jnz     short loc_180074127
0x180074164  mov     eax, [rbp+var_26]
0x180074167  mov     [rbx+2], eax
0x18007416a  movzx   eax, [rbp+var_22]
0x18007416e  mov     [rbx+6], ax
0x180074172  mov     rax, [rbp+var_20]
0x180074176  mov     [rbx+8], rax
0x18007417a  mov     rax, [rbp+var_18]
0x18007417e  mov     [rbx+10h], rax
0x180074182  mov     [rbx], r15w
0x180074186  jmp     short loc_180074127
0x180074188  mov     eax, 800A000Dh
0x18007418d  add     rsp, 48h
0x180074191  pop     r15
0x180074193  pop     r14
0x180074195  pop     r13
0x180074197  pop     r12
0x180074199  pop     rdi
0x18007419a  pop     rsi
0x18007419b  pop     rbx
0x18007419c  pop     rbp
0x18007419d  retn
```
