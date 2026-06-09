# TdiHandlePnpOperation

- ea: `0x140001df0`
- end: `0x1400021ef`
- name: `TdiHandlePnpOperation`
- size: `1023`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400032e0`

## callees

- `0x140001340`
- `0x140001df0`
- `0x140002200`
- `0x140002590`
- `0x1400041d0`
- `0x140005530`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140001e96`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140001fd5`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140001e96`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140001fd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001e25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001e36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001fba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002058`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002111`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002159`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400021de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001e25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001e36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001fba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002058`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002111`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002159`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400021de`

## pseudocode

```c
void __fastcall TdiHandlePnpOperation(const UNICODE_STRING **a1, __int64 a2, __int64 a3)
{
  const UNICODE_STRING *v3; // r14
  int v5; // ebp
  __int64 i; // rbx
  int v9; // ebp
  void (__fastcall *v10)(__int64, _QWORD, __int64); // rax
  void (__fastcall *v11)(__int64, _QWORD, __int64); // rax
  int v12; // ebp
  int v13; // ebp
  int v14; // ebp
  PWSTR v15; // rdx
  __int64 v16; // rcx
  PWSTR v17; // rax
  PVOID v18; // rbx
  PWSTR Buffer; // rcx
  int v20; // eax
  int v21; // ecx
  __int64 v22; // rax
  unsigned int (__fastcall *v23)(_QWORD, __int64, _QWORD, _QWORD); // rax
  int v24; // eax
  void (__fastcall *v25)(__int64, _QWORD, __int64); // rax
  __int64 v26; // rcx
  PWSTR v27; // rcx
  __int64 v28; // rcx
  WCHAR *v29; // rbp
  PWSTR v30; // rcx
  __int64 v31; // rcx
  PWSTR v32; // rax
  PVOID v33; // rbx
  __int64 v34; // [rsp+30h] [rbp-28h] BYREF
  __int64 *v35; // [rsp+38h] [rbp-20h]
  PVOID P; // [rsp+60h] [rbp+8h] BYREF

  v3 = *a1;
  v5 = *(_DWORD *)(a2 + 36);
  while ( 1 )
  {
    if ( v3 == (const UNICODE_STRING *)a1 )
      goto LABEL_3;
    if ( !RtlCompareUnicodeString(*(PCUNICODE_STRING *)a2, v3 + 2, 1u) )
      break;
    v3 = *(const UNICODE_STRING **)&v3->Length;
  }
  Buffer = v3[5].Buffer;
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0);
  TdipBuildProviderList(v3);
  if ( v5 != 3 )
  {
    if ( v5 == 7 )
    {
LABEL_44:
      v28 = *(_QWORD *)(a2 + 16);
      P = 0;
      if ( v28 )
      {
        TdipAddMultiSzToMultiSz(v28, v3[6].Buffer, &P);
        v29 = (WCHAR *)P;
        if ( P )
        {
          v30 = v3[6].Buffer;
          if ( v30 )
            ExFreePoolWithTag(v30, 0);
          v3[6].Buffer = v29;
        }
      }
      if ( *(_QWORD *)&v3[3].Length )
      {
        v31 = *(unsigned int *)&v3[6].Length;
        v35 = qword_140007160;
        v32 = v3[5].Buffer;
        v34 = 262146;
        P = 0;
        if ( !(unsigned int)TdipAddMultiSzToMultiSz(&v34, &v32[4 * v31], &P) )
        {
          v33 = P;
          TdipRemoveMultiSzFromMultiSz(v3[6].Buffer, P);
          (*(void (__fastcall **)(__int64, _QWORD, PVOID))&v3[3].Length)(3, *(_QWORD *)(a2 + 8), v33);
          ExFreePoolWithTag(v33, 0x6A494454u);
        }
      }
      goto LABEL_3;
    }
    if ( v5 == 8 )
      goto LABEL_22;
    for ( i = PnpHandlerProviderList; ; i = *(_QWORD *)i )
    {
      while ( 1 )
      {
        if ( (__int64 *)i == &PnpHandlerProviderList )
        {
          v11 = *(void (__fastcall **)(__int64, _QWORD, __int64))&v3[3].Length;
          if ( v11 )
            v11(3, *(_QWORD *)(a2 + 8), (__int64)&v3[5].Buffer[4 * *(unsigned int *)&v3[6].Length]);
          goto LABEL_3;
        }
        if ( !*(_BYTE *)(i + 16) )
          break;
        i = *(_QWORD *)i;
      }
      if ( !RtlCompareUnicodeString(*(PCUNICODE_STRING *)(a2 + 8), (PCUNICODE_STRING)(i + 120), 1u) )
        break;
    }
    v9 = v5 - 1;
    if ( !v9 )
    {
      TdipMultiSzStrStr(v3[5].Buffer, i + 120);
      v10 = *(void (__fastcall **)(__int64, _QWORD, __int64))&v3[3].Length;
      if ( v10 )
        v10(1, *(_QWORD *)(a2 + 8), (__int64)&v3[5].Buffer[4 * *(unsigned int *)&v3[6].Length]);
      goto LABEL_3;
    }
    v12 = v9 - 1;
    if ( v12 )
    {
      v13 = v12 - 2;
      if ( v13 )
      {
        v14 = v13 - 3;
        if ( !v14 )
          goto LABEL_44;
        if ( v14 == 1 )
        {
LABEL_22:
          v15 = v3[6].Buffer;
          if ( v15 )
          {
            v26 = *(_QWORD *)(a2 + 16);
            if ( v26 )
            {
              TdipRemoveMultiSzFromMultiSz(*(wchar_t **)(v26 + 8), v15);
              v27 = v3[6].Buffer;
              if ( *v27 )
              {
                ExFreePoolWithTag(v27, 0);
                v3[6].Buffer = 0;
              }
            }
          }
          if ( *(_QWORD *)&v3[3].Length )
          {
            v16 = *(unsigned int *)&v3[6].Length;
            v35 = qword_140007160;
            v17 = v3[5].Buffer;
            v34 = 262146;
            P = 0;
            TdipAddMultiSzToMultiSz(&v34, &v17[4 * v16], &P);
            v18 = P;
            TdipRemoveMultiSzFromMultiSz(v3[6].Buffer, P);
            (*(void (__fastcall **)(__int64, _QWORD, PVOID))&v3[3].Length)(3, *(_QWORD *)(a2 + 8), v18);
            ExFreePoolWithTag(v18, 0x6A494454u);
          }
        }
        goto LABEL_3;
      }
    }
    else if ( *(_QWORD *)&v3[5].Length )
    {
      *(_DWORD *)a3 = 2;
      *(_QWORD *)(a3 + 8) = 0;
      *(_DWORD *)(a3 + 16) = 0;
      v24 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))&v3[5].Length)(*(_QWORD *)(a2 + 8), a3, 0, 0);
      if ( v24 == 259 )
        return;
      if ( v24 )
      {
LABEL_3:
        ExFreePoolWithTag(*(PVOID *)(a3 + 88), 0);
        ExFreePoolWithTag((PVOID)a3, 0);
        return;
      }
    }
    v25 = *(void (__fastcall **)(__int64, _QWORD, __int64))&v3[3].Length;
    if ( v25 )
      v25(2, *(_QWORD *)(a2 + 8), (__int64)&v3[5].Buffer[4 * *(unsigned int *)&v3[6].Length]);
    goto LABEL_3;
  }
  v20 = *(_DWORD *)(a2 + 32);
  if ( v20 )
  {
    *(_DWORD *)(a3 + 16) = v20;
    v21 = 4;
    v22 = *(_QWORD *)(a2 + 24);
  }
  else
  {
    *(_DWORD *)(a3 + 16) = **(unsigned __int16 **)(a2 + 16);
    v21 = 5;
    v22 = *(_QWORD *)(*(_QWORD *)(a2 + 16) + 8LL);
  }
  *(_QWORD *)(a3 + 8) = v22;
  *(_DWORD *)a3 = v21;
  v23 = *(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))&v3[5].Length;
  if ( !v23 || v23(*(_QWORD *)(a2 + 8), a3, 0, 0) != 259 )
    goto LABEL_3;
}

```

## disassembly

```asm
0x140001df0  mov     [rsp+arg_10], rbx
0x140001df5  mov     [rsp+arg_18], rbp
0x140001dfa  push    rsi
0x140001dfb  push    rdi
0x140001dfc  push    r14
0x140001dfe  sub     rsp, 40h
0x140001e02  mov     r14, [rcx]
0x140001e05  mov     rsi, r8
0x140001e08  mov     ebp, [rdx+24h]
0x140001e0b  mov     rdi, rdx
0x140001e0e  mov     rbx, rcx
0x140001e11  mov     [rsp+58h+arg_8], r15
0x140001e16  cmp     r14, rbx
0x140001e19  jnz     loc_140001FCB
0x140001e1f  mov     rcx, [rsi+58h]; P
0x140001e23  xor     edx, edx; Tag
0x140001e25  call    cs:__imp_ExFreePoolWithTag
0x140001e2c  nop     dword ptr [rax+rax+00h]
0x140001e31  xor     edx, edx; Tag
0x140001e33  mov     rcx, rsi; P
0x140001e36  call    cs:__imp_ExFreePoolWithTag
0x140001e3d  nop     dword ptr [rax+rax+00h]
0x140001e42  mov     r15, [rsp+58h+arg_8]
0x140001e47  mov     rbx, [rsp+58h+arg_10]
0x140001e4c  mov     rbp, [rsp+58h+arg_18]
0x140001e51  add     rsp, 40h
0x140001e55  pop     r14
0x140001e57  pop     rdi
0x140001e58  pop     rsi
0x140001e59  retn
0x140001e5b  cmp     ebp, 7
0x140001e5e  jz      loc_140002126
0x140001e64  cmp     ebp, 8
0x140001e67  jz      loc_140001F3E
0x140001e6d  mov     rbx, cs:PnpHandlerProviderList
0x140001e74  lea     r15, PnpHandlerProviderList
0x140001e7b  nop     dword ptr [rax+rax+00h]
0x140001e80  cmp     rbx, r15
0x140001e83  jz      short loc_140001EEE
0x140001e85  cmp     byte ptr [rbx+10h], 0
0x140001e89  jnz     short loc_140001EAB
0x140001e8b  mov     rcx, [rdi+8]; String1
0x140001e8f  lea     rdx, [rbx+78h]; String2
0x140001e93  mov     r8b, 1; CaseInSensitive
0x140001e96  call    cs:__imp_RtlCompareUnicodeString
0x140001e9d  nop     dword ptr [rax+rax+00h]
0x140001ea2  test    eax, eax
0x140001ea4  jz      short loc_140001EB0
0x140001ea6  mov     rbx, [rbx]
0x140001ea9  jmp     short loc_140001E80
0x140001eab  mov     rbx, [rbx]
0x140001eae  jmp     short loc_140001E80
0x140001eb0  sub     ebp, 1
0x140001eb3  jnz     short loc_140001F1A
0x140001eb5  mov     rcx, [r14+58h]
0x140001eb9  lea     rdx, [rbx+78h]
0x140001ebd  call    TdipMultiSzStrStr
0x140001ec2  mov     rax, [r14+30h]
0x140001ec6  test    rax, rax
0x140001ec9  jz      loc_140001E1F
0x140001ecf  mov     edx, [r14+60h]
0x140001ed3  mov     rcx, [r14+58h]
0x140001ed7  lea     r8, [rcx+rdx*8]
0x140001edb  mov     rdx, [rdi+8]
0x140001edf  mov     ecx, 1
0x140001ee4  call    _guard_dispatch_icall
0x140001ee9  jmp     loc_140001E1F
0x140001eee  mov     rax, [r14+30h]
0x140001ef2  test    rax, rax
0x140001ef5  jz      loc_140001E1F
0x140001efb  mov     edx, [r14+60h]
0x140001eff  mov     rcx, [r14+58h]
0x140001f03  lea     r8, [rcx+rdx*8]
0x140001f07  mov     rdx, [rdi+8]
0x140001f0b  mov     ecx, 3
0x140001f10  call    _guard_dispatch_icall
0x140001f15  jmp     loc_140001E1F
0x140001f1a  sub     ebp, 1
0x140001f1d  jz      loc_14000207C
0x140001f23  sub     ebp, 2
0x140001f26  jz      loc_1400020BE
0x140001f2c  sub     ebp, 3
0x140001f2f  jz      loc_140002126
0x140001f35  cmp     ebp, 1
0x140001f38  jnz     loc_140001E1F
0x140001f3e  mov     rdx, [r14+68h]; void *
0x140001f42  xor     ebx, ebx
0x140001f44  test    rdx, rdx
0x140001f47  jnz     loc_1400020EC
0x140001f4d  cmp     [r14+30h], rbx
0x140001f51  jz      loc_140001E1F
0x140001f57  mov     ecx, [r14+60h]
0x140001f5b  lea     rax, qword_140007160
0x140001f62  mov     [rsp+58h+var_20], rax
0x140001f67  lea     r8, [rsp+58h+P]
0x140001f6c  mov     rax, [r14+58h]
0x140001f70  mov     [rsp+58h+var_28], 40002h
0x140001f79  mov     [rsp+58h+P], rbx
0x140001f7e  lea     rdx, [rax+rcx*8]
0x140001f82  lea     rcx, [rsp+58h+var_28]
0x140001f87  call    TdipAddMultiSzToMultiSz
0x140001f8c  mov     rbx, [rsp+58h+P]
0x140001f91  mov     rcx, [r14+68h]; Str2
0x140001f95  mov     rdx, rbx; void *
0x140001f98  call    TdipRemoveMultiSzFromMultiSz
0x140001f9d  mov     rax, [r14+30h]
0x140001fa1  mov     r8, rbx
0x140001fa4  mov     rdx, [rdi+8]
0x140001fa8  mov     ecx, 3
0x140001fad  call    _guard_dispatch_icall
0x140001fb2  mov     edx, 6A494454h; Tag
0x140001fb7  mov     rcx, rbx; P
0x140001fba  call    cs:__imp_ExFreePoolWithTag
0x140001fc1  nop     dword ptr [rax+rax+00h]
0x140001fc6  jmp     loc_140001E1F
0x140001fcb  mov     rcx, [rdi]; String1
0x140001fce  lea     rdx, [r14+20h]; String2
0x140001fd2  mov     r8b, 1; CaseInSensitive
0x140001fd5  call    cs:__imp_RtlCompareUnicodeString
0x140001fdc  nop     dword ptr [rax+rax+00h]
0x140001fe1  test    eax, eax
0x140001fe3  jnz     loc_140002074
0x140001fe9  mov     rcx, [r14+58h]; P
0x140001fed  test    rcx, rcx
0x140001ff0  jnz     short loc_140002056
0x140001ff2  mov     rcx, r14
0x140001ff5  call    TdipBuildProviderList
0x140001ffa  cmp     ebp, 3
0x140001ffd  jnz     loc_140001E5B
0x140002003  mov     eax, [rdi+20h]
0x140002006  test    eax, eax
0x140002008  jnz     short loc_140002066
0x14000200a  mov     rax, [rdi+10h]
0x14000200e  movzx   ecx, word ptr [rax]
0x140002011  mov     [rsi+10h], ecx
0x140002014  mov     ecx, 5
0x140002019  mov     rax, [rdi+10h]
0x14000201d  mov     rax, [rax+8]
0x140002021  mov     [rsi+8], rax
0x140002025  mov     [rsi], ecx
0x140002027  mov     rax, [r14+50h]
0x14000202b  test    rax, rax
0x14000202e  jz      loc_140001E1F
0x140002034  mov     rcx, [rdi+8]
0x140002038  xor     r9d, r9d
0x14000203b  xor     r8d, r8d
0x14000203e  mov     rdx, rsi
0x140002041  call    _guard_dispatch_icall
0x140002046  cmp     eax, 103h
0x14000204b  jnz     loc_140001E1F
0x140002051  jmp     loc_140001E42
0x140002056  xor     edx, edx; Tag
0x140002058  call    cs:__imp_ExFreePoolWithTag
0x14000205f  nop     dword ptr [rax+rax+00h]
0x140002064  jmp     short loc_140001FF2
0x140002066  mov     [rsi+10h], eax
0x140002069  mov     ecx, 4
0x14000206e  mov     rax, [rdi+18h]
0x140002072  jmp     short loc_140002021
0x140002074  mov     r14, [r14]
0x140002077  jmp     loc_140001E16
0x14000207c  cmp     qword ptr [r14+50h], 0
0x140002081  jz      short loc_1400020BE
0x140002083  xor     ebx, ebx
0x140002085  mov     ebp, 2
0x14000208a  mov     [rsi], ebp
0x14000208c  xor     r9d, r9d
0x14000208f  mov     [rsi+8], rbx
0x140002093  xor     r8d, r8d
0x140002096  mov     [rsi+10h], ebx
0x140002099  mov     rdx, rsi
0x14000209c  mov     rax, [r14+50h]
0x1400020a0  mov     rcx, [rdi+8]
0x1400020a4  call    _guard_dispatch_icall
0x1400020a9  cmp     eax, 103h
0x1400020ae  jz      loc_140001E42
0x1400020b4  test    eax, eax
0x1400020b6  jnz     loc_140001E1F
0x1400020bc  jmp     short loc_1400020C3
0x1400020be  mov     ebp, 2
0x1400020c3  mov     rax, [r14+30h]
0x1400020c7  test    rax, rax
0x1400020ca  jz      loc_140001E1F
0x1400020d0  mov     rdx, [r14+58h]
0x1400020d4  mov     ecx, ebp
0x1400020d6  mov     r8d, [r14+60h]
0x1400020da  lea     r8, [rdx+r8*8]
0x1400020de  mov     rdx, [rdi+8]
0x1400020e2  call    _guard_dispatch_icall
0x1400020e7  jmp     loc_140001E1F
0x1400020ec  mov     rcx, [rdi+10h]
0x1400020f0  test    rcx, rcx
0x1400020f3  jz      loc_140001F4D
0x1400020f9  mov     rcx, [rcx+8]; Str2
0x1400020fd  call    TdipRemoveMultiSzFromMultiSz
0x140002102  mov     rcx, [r14+68h]; P
0x140002106  cmp     [rcx], bx
0x140002109  jz      loc_140001F4D
0x14000210f  xor     edx, edx; Tag
0x140002111  call    cs:__imp_ExFreePoolWithTag
0x140002118  nop     dword ptr [rax+rax+00h]
0x14000211d  mov     [r14+68h], rbx
0x140002121  jmp     loc_140001F4D
0x140002126  mov     rcx, [rdi+10h]
0x14000212a  xor     ebx, ebx
0x14000212c  mov     [rsp+58h+P], rbx
0x140002131  test    rcx, rcx
0x140002134  jz      short loc_140002169
0x140002136  mov     rdx, [r14+68h]
0x14000213a  lea     r8, [rsp+58h+P]
0x14000213f  call    TdipAddMultiSzToMultiSz
0x140002144  mov     rbp, [rsp+58h+P]
0x140002149  test    rbp, rbp
0x14000214c  jz      short loc_140002169
0x14000214e  mov     rcx, [r14+68h]; P
0x140002152  test    rcx, rcx
0x140002155  jz      short loc_140002165
0x140002157  xor     edx, edx; Tag
0x140002159  call    cs:__imp_ExFreePoolWithTag
0x140002160  nop     dword ptr [rax+rax+00h]
0x140002165  mov     [r14+68h], rbp
0x140002169  cmp     [r14+30h], rbx
0x14000216d  jz      loc_140001E1F
0x140002173  mov     ecx, [r14+60h]
0x140002177  lea     rax, qword_140007160
0x14000217e  mov     [rsp+58h+var_20], rax
0x140002183  lea     r8, [rsp+58h+P]
0x140002188  mov     rax, [r14+58h]
0x14000218c  mov     [rsp+58h+var_28], 40002h
0x140002195  mov     [rsp+58h+P], rbx
0x14000219a  lea     rdx, [rax+rcx*8]
0x14000219e  lea     rcx, [rsp+58h+var_28]
0x1400021a3  call    TdipAddMultiSzToMultiSz
0x1400021a8  test    eax, eax
0x1400021aa  jnz     loc_140001E1F
0x1400021b0  mov     rbx, [rsp+58h+P]
0x1400021b5  mov     rcx, [r14+68h]; Str2
0x1400021b9  mov     rdx, rbx; void *
0x1400021bc  call    TdipRemoveMultiSzFromMultiSz
0x1400021c1  mov     rax, [r14+30h]
0x1400021c5  mov     r8, rbx
0x1400021c8  mov     rdx, [rdi+8]
0x1400021cc  mov     ecx, 3
0x1400021d1  call    _guard_dispatch_icall
0x1400021d6  mov     edx, 6A494454h; Tag
0x1400021db  mov     rcx, rbx; P
0x1400021de  call    cs:__imp_ExFreePoolWithTag
0x1400021e5  nop     dword ptr [rax+rax+00h]
0x1400021ea  jmp     loc_140001E1F
```
