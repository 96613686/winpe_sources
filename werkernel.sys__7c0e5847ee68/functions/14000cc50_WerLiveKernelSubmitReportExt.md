# WerLiveKernelSubmitReportExt

- ea: `0x14000cc50`
- end: `0x14000ce60`
- name: `WerLiveKernelSubmitReportExt`
- size: `528`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140001008`
- `0x1400018bc`
- `0x140002750`
- `0x14000cc50`
- `0x1400100f4`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000cc92`
- `ntoskrnl!DbgPrintEx` at `0x14000ccb0`
- `ntoskrnl!DbgPrintEx` at `0x14000ccfa`
- `ntoskrnl!DbgPrintEx` at `0x14000ce4c`
- `ntoskrnl!DbgPrintEx` at `0x14000cc92`
- `ntoskrnl!DbgPrintEx` at `0x14000ccb0`
- `ntoskrnl!DbgPrintEx` at `0x14000ccfa`
- `ntoskrnl!DbgPrintEx` at `0x14000ce4c`

## string_xrefs

- `0x14000ce3f`: `WERKERNELHOST: EtwWrite failed with 0x%X\n`

## pseudocode

```c
__int64 __fastcall WerLiveKernelSubmitReportExt(_DWORD *a1)
{
  int v3; // eax
  int v4; // edx
  int v5; // r9d
  unsigned int v6; // r14d
  int v7; // ecx
  __int64 v8; // rcx
  __int64 *v9; // rax
  int v10; // r8d
  __int64 v11; // rdx
  int v12; // edx
  __int64 *v13; // rax
  int v14; // eax
  int v15; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v16; // [rsp+34h] [rbp-55h] BYREF
  __int64 v17; // [rsp+38h] [rbp-51h] BYREF
  __int64 v18[7]; // [rsp+40h] [rbp-49h] BYREF
  int v19; // [rsp+78h] [rbp-11h]
  int v20; // [rsp+7Ch] [rbp-Dh]
  int *v21; // [rsp+80h] [rbp-9h]
  __int64 v22; // [rsp+88h] [rbp-1h]
  __int64 *v23; // [rsp+90h] [rbp+7h]
  int v24; // [rsp+98h] [rbp+Fh]
  int v25; // [rsp+9Ch] [rbp+13h]
  unsigned int *v26; // [rsp+A0h] [rbp+17h]
  __int64 v27; // [rsp+A8h] [rbp+1Fh]

  if ( !a1 )
    goto LABEL_4;
  if ( *a1 != 1667984471 )
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: WER context signature validation failed! \n");
LABEL_4:
    DbgPrintEx(5u, 1u, "WERKERNELHOST: WerLiveKernelSubmitReportExt: Invalid report handle passed %p\n", a1);
    return 3221225485LL;
  }
  v3 = WerpSubmitReport((__int64)a1);
  v6 = v3;
  if ( v3 < 0 )
    DbgPrintEx(5u, 1u, "WERKERNELHOST: WerLiveKernelSubmitReport failed with status 0x%X\n", v3);
  v7 = dword_140009048;
  if ( (unsigned int)dword_140009048 > 5 )
  {
    v7 = qword_140009060;
    v4 = 0;
    if ( (qword_140009058 & 0x400000000000LL) != 0
      && (*(_QWORD *)&qword_140009060 & 0x400000000000LL) == *(_QWORD *)&qword_140009060 )
    {
      v17 = 50331648;
      v18[4] = (__int64)&v17;
      v8 = -1;
      v9 = (__int64 *)(a1 + 6);
      v18[5] = 8;
      v10 = 2;
      if ( a1 == (_DWORD *)-24LL )
      {
        v9 = &qword_1400059C8;
        v12 = 2;
      }
      else
      {
        v11 = -1;
        do
          ++v11;
        while ( *((_WORD *)v9 + v11) );
        v12 = 2 * v11 + 2;
      }
      v18[6] = (__int64)v9;
      v15 = a1[1];
      v21 = &v15;
      v13 = (__int64 *)(a1 + 14);
      v19 = v12;
      v20 = 0;
      v22 = 4;
      if ( a1 == (_DWORD *)-56LL )
      {
        v13 = &qword_1400059C8;
      }
      else
      {
        do
          ++v8;
        while ( *((_WORD *)v13 + v8) );
        v10 = 2 * v8 + 2;
      }
      v23 = v13;
      v24 = v10;
      v26 = &v16;
      v25 = 0;
      v16 = v6;
      v27 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v8, (int)&dword_140008094, v10, v5, 7u, (__int64)v18);
    }
  }
  if ( (Microsoft_Windows_WerKernelEnableBits & 1) != 0 )
  {
    v14 = McTemplateU0zqzq_EtwWriteTransfer(v7, v4, (int)a1 + 24, a1[1], (__int64)(a1 + 14), v6);
    if ( v14 < 0 )
      DbgPrintEx(5u, 1u, "WERKERNELHOST: EtwWrite failed with 0x%X\n", v14);
  }
  return v6;
}

```

## disassembly

```asm
0x14000cc50  push    rbp
0x14000cc52  push    rbx
0x14000cc53  push    r14
0x14000cc55  push    r15
0x14000cc57  lea     rbp, [rsp-3Fh]
0x14000cc5c  sub     rsp, 0C8h
0x14000cc63  mov     rax, cs:__security_cookie
0x14000cc6a  xor     rax, rsp
0x14000cc6d  mov     [rbp+57h+var_30], rax
0x14000cc71  xor     r15d, r15d
0x14000cc74  mov     rbx, rcx
0x14000cc77  test    rcx, rcx
0x14000cc7a  jz      short loc_14000CC9E
0x14000cc7c  cmp     dword ptr [rcx], 636B6C57h
0x14000cc82  jz      short loc_14000CCDC
0x14000cc84  lea     edx, [r15+1]; Level
0x14000cc88  lea     ecx, [rdx+4]; ComponentId
0x14000cc8b  lea     r8, aWerkernelhostW_8; "WERKERNELHOST: WER context signature va"...
0x14000cc92  call    cs:__imp_DbgPrintEx
0x14000cc99  nop     dword ptr [rax+rax+00h]
0x14000cc9e  mov     edx, 1; Level
0x14000cca3  lea     r8, aWerkernelhostW_15; "WERKERNELHOST: WerLiveKernelSubmitRepor"...
0x14000ccaa  mov     r9, rbx
0x14000ccad  lea     ecx, [rdx+4]; ComponentId
0x14000ccb0  call    cs:__imp_DbgPrintEx
0x14000ccb7  nop     dword ptr [rax+rax+00h]
0x14000ccbc  mov     eax, 0C000000Dh
0x14000ccc1  mov     rcx, [rbp+57h+var_30]
0x14000ccc5  xor     rcx, rsp; StackCookie
0x14000ccc8  call    __security_check_cookie
0x14000cccd  add     rsp, 0C8h
0x14000ccd4  pop     r15
0x14000ccd6  pop     r14
0x14000ccd8  pop     rbx
0x14000ccd9  pop     rbp
0x14000ccda  retn
0x14000ccdc  call    WerpSubmitReport
0x14000cce1  mov     r14d, eax
0x14000cce4  test    eax, eax
0x14000cce6  jns     short loc_14000CD06
0x14000cce8  mov     edx, 1; Level
0x14000cced  lea     r8, aWerkernelhostW_4; "WERKERNELHOST: WerLiveKernelSubmitRepor"...
0x14000ccf4  mov     r9d, eax
0x14000ccf7  lea     ecx, [rdx+4]; ComponentId
0x14000ccfa  call    cs:__imp_DbgPrintEx
0x14000cd01  nop     dword ptr [rax+rax+00h]
0x14000cd06  mov     ecx, cs:dword_140009048
0x14000cd0c  cmp     ecx, 5
0x14000cd0f  jbe     loc_14000CE12
0x14000cd15  mov     rcx, cs:qword_140009060
0x14000cd1c  mov     rdx, 400000000000h
0x14000cd26  mov     rax, cs:qword_140009058
0x14000cd2d  test    rdx, rax
0x14000cd30  jz      loc_14000CE12
0x14000cd36  mov     rax, rcx
0x14000cd39  and     rax, rdx
0x14000cd3c  cmp     rax, rcx
0x14000cd3f  jnz     loc_14000CE12
0x14000cd45  lea     rax, [rbp+57h+var_A8]
0x14000cd49  mov     [rbp+57h+var_A8], 3000000h
0x14000cd51  mov     [rbp+57h+var_80], rax
0x14000cd55  or      rcx, 0FFFFFFFFFFFFFFFFh; int
0x14000cd59  lea     rax, [rbx+18h]
0x14000cd5d  mov     [rbp+57h+var_78], 8
0x14000cd65  mov     r8d, 2; int
0x14000cd6b  test    rax, rax
0x14000cd6e  jz      short loc_14000CD86
0x14000cd70  mov     rdx, rcx
0x14000cd73  inc     rdx
0x14000cd76  cmp     [rax+rdx*2], r15w
0x14000cd7b  jnz     short loc_14000CD73
0x14000cd7d  lea     edx, ds:2[rdx*2]
0x14000cd84  jmp     short loc_14000CD90
0x14000cd86  lea     rax, qword_1400059C8
0x14000cd8d  mov     edx, r8d
0x14000cd90  mov     [rbp+57h+var_70], rax
0x14000cd94  mov     eax, [rbx+4]
0x14000cd97  mov     [rbp+57h+var_B0], eax
0x14000cd9a  lea     rax, [rbp+57h+var_B0]
0x14000cd9e  mov     [rbp+57h+var_60], rax
0x14000cda2  lea     rax, [rbx+38h]
0x14000cda6  mov     [rbp+57h+var_68], edx
0x14000cda9  mov     [rbp+57h+var_64], r15d
0x14000cdad  mov     [rbp+57h+var_58], 4
0x14000cdb5  test    rax, rax
0x14000cdb8  jz      short loc_14000CDCE
0x14000cdba  inc     rcx
0x14000cdbd  cmp     [rax+rcx*2], r15w
0x14000cdc2  jnz     short loc_14000CDBA
0x14000cdc4  lea     r8d, ds:2[rcx*2]
0x14000cdcc  jmp     short loc_14000CDD5
0x14000cdce  lea     rax, qword_1400059C8
0x14000cdd5  mov     [rbp+57h+var_50], rax
0x14000cdd9  lea     rdx, dword_140008094; int
0x14000cde0  lea     rax, [rbp+57h+var_AC]
0x14000cde4  mov     [rbp+57h+var_48], r8d
0x14000cde8  mov     [rbp+57h+var_40], rax
0x14000cdec  lea     rax, [rbp+57h+var_A0]
0x14000cdf0  mov     [rsp+0E0h+var_B8], rax; __int64
0x14000cdf5  mov     [rsp+0E0h+var_C0], 7; ULONG
0x14000cdfd  mov     [rbp+57h+var_44], r15d
0x14000ce01  mov     [rbp+57h+var_AC], r14d
0x14000ce05  mov     [rbp+57h+var_38], 4
0x14000ce0d  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ce12  test    cs:Microsoft_Windows_WerKernelEnableBits, 1
0x14000ce19  jz      short loc_14000CE58
0x14000ce1b  mov     r9d, [rbx+4]
0x14000ce1f  lea     rax, [rbx+38h]
0x14000ce23  lea     r8, [rbx+18h]
0x14000ce27  mov     dword ptr [rsp+0E0h+var_B8], r14d
0x14000ce2c  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14000ce31  call    McTemplateU0zqzq_EtwWriteTransfer
0x14000ce36  test    eax, eax
0x14000ce38  jns     short loc_14000CE58
0x14000ce3a  mov     edx, 1; Level
0x14000ce3f  lea     r8, aWerkernelhostE; "WERKERNELHOST: EtwWrite failed with 0x%"...
0x14000ce46  mov     r9d, eax
0x14000ce49  lea     ecx, [rdx+4]; ComponentId
0x14000ce4c  call    cs:__imp_DbgPrintEx
0x14000ce53  nop     dword ptr [rax+rax+00h]
0x14000ce58  mov     eax, r14d
0x14000ce5b  jmp     loc_14000CCC1
```
