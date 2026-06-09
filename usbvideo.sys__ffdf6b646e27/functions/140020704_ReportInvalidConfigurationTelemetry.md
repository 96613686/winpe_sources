# ReportInvalidConfigurationTelemetry

- ea: `0x140020704`
- end: `0x1400208e8`
- name: `ReportInvalidConfigurationTelemetry`
- size: `484`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140015e60`
- `0x14002f3e8`
- `0x14002f8cc`

## callees

- `0x140001008`
- `0x140001048`
- `0x140001078`
- `0x14001f25c`
- `0x140020704`
- `0x140040a30`

## pseudocode

```c
NTSTATUS __fastcall ReportInvalidConfigurationTelemetry(_QWORD *a1, int a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v4; // r13
  __int64 v5; // rbx
  __int64 v8; // rdi
  int TextStringValueFromStringDescriptor; // eax
  __int64 v10; // r8
  _BYTE *v11; // r14
  NTSTATUS result; // eax
  __int64 v13; // rdx
  int v14; // ecx
  const wchar_t *v15; // rdx
  __int64 v16; // r9
  __int64 v17; // r10
  __int64 v18; // r8
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  int v21; // [rsp+38h] [rbp-C8h] BYREF
  int v22; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  __int64 v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+88h] [rbp-78h]
  _BYTE v29[16]; // [rsp+90h] [rbp-70h] BYREF
  int *v30; // [rsp+A0h] [rbp-60h]
  __int64 v31; // [rsp+A8h] [rbp-58h]
  int *v32; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  int *v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C8h] [rbp-38h]
  _BYTE v36[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v37[16]; // [rsp+E0h] [rbp-20h] BYREF
  int *v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+F8h] [rbp-8h]
  _BYTE v40[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v41[64]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v42[64]; // [rsp+150h] [rbp+50h] BYREF

  v3 = a1[1];
  v4 = a3;
  v5 = a1[2];
  v8 = *(_QWORD *)(*a1 + 24LL);
  LOBYTE(a3) = *(_BYTE *)(v3 + 14);
  TextStringValueFromStringDescriptor = GetTextStringValueFromStringDescriptor(v8, v5, a3, v41);
  v10 = 0;
  v11 = v41;
  if ( TextStringValueFromStringDescriptor < 0 )
    v11 = 0;
  LOBYTE(v10) = *(_BYTE *)(v3 + 15);
  GetTextStringValueFromStringDescriptor(v8, v5, v10, v42);
  result = dword_14004C1E8;
  if ( dword_14004C1E8 )
  {
    result = tlgKeywordOn(&dword_14004C1E8, 0x400000000000LL);
    if ( (_BYTE)result )
    {
      v13 = *a1;
      v25 = &v23;
      v23 = 33556480;
      v26 = 8;
      v28 = 16;
      v27 = v13 + 1348;
      tlgCreate1Sz_wchar_t(v29, *(_QWORD *)(v13 + 1368));
      v14 = *(unsigned __int16 *)(v3 + 8);
      v30 = &v19;
      v15 = (const wchar_t *)(v11 + 2);
      v20 = *(unsigned __int16 *)(v3 + 10);
      v32 = &v20;
      v21 = *(unsigned __int16 *)(v3 + 12);
      v34 = &v21;
      v19 = v14;
      v31 = 4;
      v33 = 4;
      v35 = 4;
      if ( !v11 )
        v15 = L"Unknown";
      tlgCreate1Sz_wchar_t(v36, v15);
      if ( v17 )
        v16 = v17 + 2;
      tlgCreate1Sz_wchar_t(v37, v16);
      v22 = a2;
      v38 = &v22;
      v39 = 4;
      tlgCreate1Sz_wchar_t(v40, v4);
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_14004C1E8,
               (unsigned __int8 *)&word_140048BF2,
               v18,
               (__int64)v24,
               0xCu,
               v24);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140020704  mov     [rsp-8+arg_8], rbx
0x140020709  push    rbp
0x14002070a  push    rsi
0x14002070b  push    rdi
0x14002070c  push    r12
0x14002070e  push    r13
0x140020710  push    r14
0x140020712  push    r15
0x140020714  lea     rbp, [rsp-0A0h]
0x14002071c  sub     rsp, 1A0h
0x140020723  mov     rax, cs:__security_cookie
0x14002072a  xor     rax, rsp
0x14002072d  mov     [rbp+0D0h+var_40], rax
0x140020734  mov     rax, [rcx]
0x140020737  lea     r9, [rbp+0D0h+var_C0]
0x14002073b  mov     rsi, [rcx+8]
0x14002073f  mov     r13, r8
0x140020742  mov     rbx, [rcx+10h]
0x140020746  mov     r12d, edx
0x140020749  mov     r15, rcx
0x14002074c  mov     rdx, rbx
0x14002074f  mov     rdi, [rax+18h]
0x140020753  mov     r8b, [rsi+0Eh]
0x140020757  mov     rcx, rdi
0x14002075a  call    GetTextStringValueFromStringDescriptor
0x14002075f  xor     r8d, r8d
0x140020762  lea     r14, [rbp+0D0h+var_C0]
0x140020766  test    eax, eax
0x140020768  lea     r9, [rbp+0D0h+var_80]
0x14002076c  mov     rdx, rbx
0x14002076f  mov     rcx, rdi
0x140020772  cmovs   r14, r8
0x140020776  mov     r8b, [rsi+0Fh]
0x14002077a  call    GetTextStringValueFromStringDescriptor
0x14002077f  xor     r11d, r11d
0x140020782  lea     r10, [rbp+0D0h+var_80]
0x140020786  test    eax, eax
0x140020788  mov     eax, cs:dword_14004C1E8
0x14002078e  cmovs   r10, r11
0x140020792  test    eax, eax
0x140020794  jz      loc_1400208BD
0x14002079a  mov     rdx, 400000000000h
0x1400207a4  lea     rcx, dword_14004C1E8
0x1400207ab  call    _tlgKeywordOn
0x1400207b0  test    al, al
0x1400207b2  jz      loc_1400208BD
0x1400207b8  mov     rdx, [r15]
0x1400207bb  lea     rax, [rsp+1D0h+var_190]
0x1400207c0  mov     [rsp+1D0h+var_160], rax
0x1400207c5  lea     rcx, [rbp+0D0h+var_140]
0x1400207c9  mov     [rsp+1D0h+var_190], 2000800h
0x1400207d2  mov     [rsp+1D0h+var_158], 8
0x1400207db  lea     rax, [rdx+544h]
0x1400207e2  mov     [rbp+0D0h+var_148], 10h
0x1400207ea  mov     [rbp+0D0h+var_150], rax
0x1400207ee  mov     rdx, [rdx+558h]
0x1400207f5  call    _tlgCreate1Sz_wchar_t
0x1400207fa  movzx   ecx, word ptr [rsi+8]
0x1400207fe  lea     rax, [rsp+1D0h+var_1A0]
0x140020803  mov     [rbp+0D0h+var_130], rax
0x140020807  lea     r9, aUnknown; "Unknown"
0x14002080e  movzx   eax, word ptr [rsi+0Ah]
0x140020812  lea     rdx, [r14+2]
0x140020816  mov     [rsp+1D0h+var_19C], eax
0x14002081a  lea     rax, [rsp+1D0h+var_19C]
0x14002081f  mov     [rbp+0D0h+var_120], rax
0x140020823  movzx   eax, word ptr [rsi+0Ch]
0x140020827  mov     [rsp+1D0h+var_198], eax
0x14002082b  lea     rax, [rsp+1D0h+var_198]
0x140020830  mov     [rbp+0D0h+var_110], rax
0x140020834  mov     [rsp+1D0h+var_1A0], ecx
0x140020838  mov     [rbp+0D0h+var_128], 4
0x140020840  mov     [rbp+0D0h+var_118], 4
0x140020848  mov     [rbp+0D0h+var_108], 4
0x140020850  test    r14, r14
0x140020853  jnz     short loc_140020858
0x140020855  mov     rdx, r9
0x140020858  lea     rcx, [rbp+0D0h+var_100]
0x14002085c  call    _tlgCreate1Sz_wchar_t
0x140020861  test    r10, r10
0x140020864  jz      short loc_14002086A
0x140020866  lea     r9, [r10+2]
0x14002086a  mov     rdx, r9
0x14002086d  lea     rcx, [rbp+0D0h+var_F0]
0x140020871  call    _tlgCreate1Sz_wchar_t
0x140020876  lea     rax, [rsp+1D0h+var_194]
0x14002087b  mov     [rsp+1D0h+var_194], r12d
0x140020880  mov     rdx, r13
0x140020883  mov     [rbp+0D0h+var_E0], rax
0x140020887  lea     rcx, [rbp+0D0h+var_D0]
0x14002088b  mov     [rbp+0D0h+var_D8], 4
0x140020893  call    _tlgCreate1Sz_wchar_t
0x140020898  lea     r9, [rsp+1D0h+var_180]; int
0x14002089d  mov     [rsp+1D0h+var_1A8], r9; __int64
0x1400208a2  lea     rdx, word_140048BF2; int
0x1400208a9  lea     rcx, dword_14004C1E8; int
0x1400208b0  mov     [rsp+1D0h+var_1B0], 0Ch; ULONG
0x1400208b8  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400208bd  mov     rcx, [rbp+0D0h+var_40]
0x1400208c4  xor     rcx, rsp; StackCookie
0x1400208c7  call    __security_check_cookie
0x1400208cc  mov     rbx, [rsp+1D0h+arg_8]
0x1400208d4  add     rsp, 1A0h
0x1400208db  pop     r15
0x1400208dd  pop     r14
0x1400208df  pop     r13
0x1400208e1  pop     r12
0x1400208e3  pop     rdi
0x1400208e4  pop     rsi
0x1400208e5  pop     rbp
0x1400208e6  retn
```
