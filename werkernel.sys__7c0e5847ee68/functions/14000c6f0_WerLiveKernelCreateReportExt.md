# WerLiveKernelCreateReportExt

- ea: `0x14000c6f0`
- end: `0x14000cb3e`
- name: `WerLiveKernelCreateReportExt`
- size: `1102`
- prototype: `__int64 __fastcall(const WCHAR *, int *, _QWORD *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140001008`
- `0x1400017e8`
- `0x140002750`
- `0x14000c6f0`
- `0x14000d174`
- `0x14000d1d0`
- `0x14000d438`
- `0x14000d9ec`
- `0x14000e194`
- `0x14000e72c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000c77a`
- `ntoskrnl!DbgPrintEx` at `0x14000c7c6`
- `ntoskrnl!DbgPrintEx` at `0x14000c843`
- `ntoskrnl!DbgPrintEx` at `0x14000c8e4`
- `ntoskrnl!DbgPrintEx` at `0x14000c933`
- `ntoskrnl!DbgPrintEx` at `0x14000c990`
- `ntoskrnl!DbgPrintEx` at `0x14000cae0`
- `ntoskrnl!DbgPrintEx` at `0x14000cb0e`
- `ntoskrnl!DbgPrintEx` at `0x14000c77a`
- `ntoskrnl!DbgPrintEx` at `0x14000c7c6`
- `ntoskrnl!DbgPrintEx` at `0x14000c843`
- `ntoskrnl!DbgPrintEx` at `0x14000c8e4`
- `ntoskrnl!DbgPrintEx` at `0x14000c933`
- `ntoskrnl!DbgPrintEx` at `0x14000c990`
- `ntoskrnl!DbgPrintEx` at `0x14000cae0`
- `ntoskrnl!DbgPrintEx` at `0x14000cb0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c969`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c969`

## string_xrefs

- `0x14000cb04`: `WERKERNELHOST: WerLiveKernelCreateReportExt: Invalid parameter\n`
- `0x14000c76c`: `WERKERNELHOST: WerLiveKernelCreateReportExt: Reports not initialized\n`
- `0x14000c836`: `WERKERNELHOST: CheckPolicy throttled dump creation for Component \n`
- `0x14000c8bb`: `WERKERNELHOST:  RtlStringCchCopyW failed to copy ComponentName, status 0x%X\n`
- `0x14000c8d2`: `WERKERNELHOST: Could not create report ID, error 0x%X\n`
- `0x14000c924`: `WERKERNELHOST: WerKernelCreateReport failed, status 0x%X\n`
- `0x14000c97a`: `WERKERNELHOST: WerLiveKernelCreateReport: returning reportHandle %p Policy %i\n`
- `0x14000cad1`: `WERKERNELHOST: EtwWrite failed with 0x%X\n`

## pseudocode

```c
__int64 __fastcall WerLiveKernelCreateReportExt(const WCHAR *a1, int *a2, _QWORD *a3)
{
  PCWSTR v5; // rsi
  signed int v6; // r13d
  bool v7; // zf
  int v8; // ecx
  int v9; // r9d
  signed int Report; // ebx
  __int64 v11; // rcx
  _WORD *v12; // rax
  int v13; // edx
  _DWORD *Mem; // rax
  _DWORD *v15; // rsi
  const WCHAR *v16; // r13
  int ReportId; // eax
  const CHAR *v18; // r8
  _WORD *v19; // r8
  __int64 v20; // rax
  const WCHAR *v21; // rcx
  __int64 v22; // rdx
  _WORD *v23; // rcx
  void *v24; // rcx
  __int64 v25; // rax
  char v26; // di
  int v27; // r12d
  int v28; // eax
  signed int v30; // [rsp+40h] [rbp-89h] BYREF
  signed int v31; // [rsp+44h] [rbp-85h] BYREF
  int v32; // [rsp+48h] [rbp-81h] BYREF
  PCWSTR SourceString; // [rsp+50h] [rbp-79h] BYREF
  __int64 v34; // [rsp+58h] [rbp-71h] BYREF
  __int64 v35[7]; // [rsp+60h] [rbp-69h] BYREF
  int v36; // [rsp+98h] [rbp-31h]
  int v37; // [rsp+9Ch] [rbp-2Dh]
  int *v38; // [rsp+A0h] [rbp-29h]
  __int64 v39; // [rsp+A8h] [rbp-21h]
  signed int *v40; // [rsp+B0h] [rbp-19h]
  __int64 v41; // [rsp+B8h] [rbp-11h]
  signed int *v42; // [rsp+C0h] [rbp-9h]
  __int64 v43; // [rsp+C8h] [rbp-1h]
  PCWSTR *p_SourceString; // [rsp+D0h] [rbp+7h]
  __int64 v45; // [rsp+D8h] [rbp+Fh]

  SourceString = a1;
  v5 = a1;
  if ( a2 )
    v32 = *a2;
  else
    v32 = 0;
  v30 = 0;
  v6 = 0;
  v31 = 0;
  if ( a1 )
  {
    if ( a3 )
    {
      if ( a2 )
      {
        v7 = WerKernelLiveReportInitialized == 0;
        *a3 = 0;
        if ( v7 )
        {
          DbgPrintEx(5u, 1u, "WERKERNELHOST: WerLiveKernelCreateReportExt: Reports not initialized\n");
          Report = -1073741822;
LABEL_14:
          v13 = 0;
          *a2 = 0;
          goto LABEL_44;
        }
        v11 = 16;
        v12 = v5;
        do
        {
          if ( !*v12 )
            break;
          ++v12;
          --v11;
        }
        while ( v11 );
        Report = v11 == 0 ? 0xC000000D : 0;
        if ( !v11 )
        {
          DbgPrintEx(5u, 1u, "WERKERNELHOST: Key key length exceeded\n");
          goto LABEL_14;
        }
        Mem = (_DWORD *)WerpAllocateMem(656, 0);
        v13 = 0;
        v15 = Mem;
        if ( !Mem )
        {
          Report = -1073741801;
          *a2 = 0;
LABEL_43:
          v5 = SourceString;
LABEL_44:
          if ( (unsigned int)dword_140009048 > 5
            && (v8 = qword_140009060, (qword_140009058 & 0x400000000000LL) != 0)
            && (*(_QWORD *)&qword_140009060 & 0x400000000000LL) == *(_QWORD *)&qword_140009060 )
          {
            v34 = 50331648;
            v35[4] = (__int64)&v34;
            v25 = -1;
            v35[5] = 8;
            do
              ++v25;
            while ( v5[v25] );
            v26 = v30;
            v27 = v32;
            v36 = 2 * v25 + 2;
            v38 = &v32;
            v40 = &v31;
            v42 = &v30;
            p_SourceString = &SourceString;
            v37 = 0;
            v35[6] = (__int64)v5;
            v39 = 4;
            v31 = v30;
            v41 = 4;
            v30 = Report;
            v43 = 4;
            LODWORD(SourceString) = v6;
            v45 = 4;
            tlgWriteTransfer_EtwWriteTransfer(qword_140009060, (int)&byte_140008011, 8, v9, 8u, (__int64)v35);
          }
          else
          {
            v27 = v32;
            v26 = v30;
          }
          if ( (Microsoft_Windows_WerKernelEnableBits & 1) != 0 )
          {
            v28 = McTemplateU0zqqqq_EtwWriteTransfer(v8, v13, (_DWORD)v5, v27, v26, Report, v6);
            if ( v28 < 0 )
              DbgPrintEx(5u, 1u, "WERKERNELHOST: EtwWrite failed with 0x%X\n", v28);
          }
          return (unsigned int)Report;
        }
        v16 = SourceString;
        *Mem = 1667984471;
        ReportId = WerpCheckPolicy(v16);
        Report = ReportId;
        if ( ReportId < 0 )
        {
          v18 = "WERKERNELHOST: CheckPolicy failed, status 0x%X\n";
LABEL_32:
          DbgPrintEx(5u, 1u, v18, (unsigned int)ReportId);
          goto LABEL_21;
        }
        if ( v30 )
        {
          v15[1] = v30;
          v19 = v15 + 6;
          v20 = 2147483646;
          v21 = v16;
          v22 = 16;
          do
          {
            if ( !v20 )
              break;
            if ( !*v21 )
              break;
            *v19++ = *v21++;
            --v20;
            --v22;
          }
          while ( v22 );
          v23 = v19 - 1;
          Report = v22 == 0 ? 0x80000005 : 0;
          if ( v22 )
            v23 = v19;
          *v23 = 0;
          if ( v22 )
          {
            ReportId = WerpCreateReportId(v15);
            Report = ReportId;
            if ( ReportId >= 0 )
            {
              Report = WerpCreateReport(v30, (_DWORD)v16, (int)v15 + 56, (int)v15 + 16, (__int64)&v31);
              if ( Report >= 0 && *((_QWORD *)v15 + 2)
                || (DbgPrintEx(5u, 1u, "WERKERNELHOST: WerKernelCreateReport failed, status 0x%X\n", Report), Report >= 0) )
              {
                DbgPrintEx(
                  5u,
                  3u,
                  "WERKERNELHOST: WerLiveKernelCreateReport: returning reportHandle %p Policy %i\n",
                  v15,
                  v15[1]);
                *a3 = v15;
                *a2 = v15[1];
LABEL_42:
                v6 = v31;
                v13 = 0;
                goto LABEL_43;
              }
              *a2 = 0;
LABEL_38:
              v24 = (void *)*((_QWORD *)v15 + 2);
              if ( v24 )
              {
                WerpCancelReport(v24);
                WerpCloseHandle(*((_QWORD *)v15 + 2));
                *((_QWORD *)v15 + 2) = 0;
              }
              ExFreePoolWithTag(v15, 0);
              goto LABEL_42;
            }
            v18 = "WERKERNELHOST: Could not create report ID, error 0x%X\n";
            goto LABEL_32;
          }
          DbgPrintEx(
            5u,
            1u,
            "WERKERNELHOST:  RtlStringCchCopyW failed to copy ComponentName, status 0x%X\n",
            (unsigned int)Report);
        }
        else
        {
          DbgPrintEx(5u, 1u, "WERKERNELHOST: CheckPolicy throttled dump creation for Component \n");
          Report = -1073741790;
        }
LABEL_21:
        *a2 = 0;
        goto LABEL_38;
      }
      goto LABEL_56;
    }
  }
  else if ( a3 )
  {
LABEL_56:
    *a3 = 0;
  }
  if ( a2 )
    *a2 = 0;
  DbgPrintEx(5u, 1u, "WERKERNELHOST: WerLiveKernelCreateReportExt: Invalid parameter\n");
  return 3221225485LL;
}

```

## disassembly

```asm
0x14000c6f0  push    rbp
0x14000c6f2  push    rbx
0x14000c6f3  push    rsi
0x14000c6f4  push    rdi
0x14000c6f5  push    r12
0x14000c6f7  push    r13
0x14000c6f9  push    r15
0x14000c6fb  lea     rbp, [rsp-27h]
0x14000c700  sub     rsp, 0F0h
0x14000c707  mov     rax, cs:__security_cookie
0x14000c70e  xor     rax, rsp
0x14000c711  mov     [rbp+57h+var_40], rax
0x14000c715  mov     rdi, rdx
0x14000c718  mov     [rbp+57h+SourceString], rcx
0x14000c71c  xor     edx, edx
0x14000c71e  mov     r12, r8
0x14000c721  mov     rsi, rcx
0x14000c724  test    rdi, rdi
0x14000c727  jz      short loc_14000C731
0x14000c729  mov     eax, [rdi]
0x14000c72b  mov     [rsp+120h+var_D8], eax
0x14000c72f  jmp     short loc_14000C735
0x14000c731  mov     [rsp+120h+var_D8], edx
0x14000c735  mov     [rsp+120h+var_E0], edx
0x14000c739  mov     r13d, edx
0x14000c73c  mov     [rsp+120h+var_DC], edx
0x14000c740  test    rsi, rsi
0x14000c743  jz      loc_14000CAF0
0x14000c749  test    r12, r12
0x14000c74c  jz      loc_14000CAF8
0x14000c752  test    rdi, rdi
0x14000c755  jz      loc_14000CAF5
0x14000c75b  cmp     cs:WerKernelLiveReportInitialized, dl
0x14000c761  mov     r15d, 5
0x14000c767  mov     [r8], rdx
0x14000c76a  jnz     short loc_14000C78D
0x14000c76c  lea     r8, aWerkernelhostW_39; "WERKERNELHOST: WerLiveKernelCreateRepor"...
0x14000c773  mov     ecx, r15d; ComponentId
0x14000c776  lea     edx, [r15-4]; Level
0x14000c77a  call    cs:__imp_DbgPrintEx
0x14000c781  nop     dword ptr [rax+rax+00h]
0x14000c786  mov     ebx, 0C0000002h
0x14000c78b  jmp     short loc_14000C7D2
0x14000c78d  mov     ecx, 10h
0x14000c792  mov     rax, rsi
0x14000c795  cmp     [rax], dx
0x14000c798  jz      short loc_14000C7A4
0x14000c79a  add     rax, 2
0x14000c79e  sub     rcx, 1
0x14000c7a2  jnz     short loc_14000C795
0x14000c7a4  mov     rax, rcx
0x14000c7a7  neg     rax
0x14000c7aa  sbb     ebx, ebx
0x14000c7ac  not     ebx
0x14000c7ae  and     ebx, 0C000000Dh
0x14000c7b4  test    rcx, rcx
0x14000c7b7  jnz     short loc_14000C7DB
0x14000c7b9  lea     edx, [rcx+1]; Level
0x14000c7bc  mov     ecx, r15d; ComponentId
0x14000c7bf  lea     r8, aWerkernelhostK; "WERKERNELHOST: Key key length exceeded"...
0x14000c7c6  call    cs:__imp_DbgPrintEx
0x14000c7cd  nop     dword ptr [rax+rax+00h]
0x14000c7d2  xor     edx, edx
0x14000c7d4  mov     [rdi], edx
0x14000c7d6  jmp     loc_14000C9B0
0x14000c7db  mov     ecx, 290h
0x14000c7e0  call    WerpAllocateMem
0x14000c7e5  xor     edx, edx
0x14000c7e7  mov     rsi, rax
0x14000c7ea  test    rax, rax
0x14000c7ed  jnz     short loc_14000C7FB
0x14000c7ef  mov     ebx, 0C0000017h
0x14000c7f4  mov     [rdi], edx
0x14000c7f6  jmp     loc_14000C9AC
0x14000c7fb  mov     r13, [rbp+57h+SourceString]
0x14000c7ff  lea     r9, [rsp+120h+var_DC]
0x14000c804  mov     dword ptr [rax], 636B6C57h
0x14000c80a  lea     r8, [rsp+120h+var_E0]
0x14000c80f  mov     edx, [rdi]
0x14000c811  mov     rcx, r13; SourceString
0x14000c814  call    WerpCheckPolicy
0x14000c819  xor     r10d, r10d
0x14000c81c  mov     ebx, eax
0x14000c81e  test    eax, eax
0x14000c820  jns     short loc_14000C82E
0x14000c822  lea     r8, aWerkernelhostC_2; "WERKERNELHOST: CheckPolicy failed, stat"...
0x14000c829  jmp     loc_14000C8D9
0x14000c82e  mov     eax, [rsp+120h+var_E0]
0x14000c832  test    eax, eax
0x14000c834  jnz     short loc_14000C85F
0x14000c836  lea     r8, aWerkernelhostC_8; "WERKERNELHOST: CheckPolicy throttled du"...
0x14000c83d  mov     ecx, r15d; ComponentId
0x14000c840  lea     edx, [rax+1]; Level
0x14000c843  call    cs:__imp_DbgPrintEx
0x14000c84a  nop     dword ptr [rax+rax+00h]
0x14000c84f  mov     ebx, 0C0000022h
0x14000c854  mov     dword ptr [rdi], 0
0x14000c85a  jmp     loc_14000C947
0x14000c85f  mov     [rsi+4], eax
0x14000c862  lea     r8, [rsi+18h]
0x14000c866  mov     eax, 7FFFFFFEh
0x14000c86b  mov     rcx, r13
0x14000c86e  mov     edx, 10h
0x14000c873  test    rax, rax
0x14000c876  jz      short loc_14000C897
0x14000c878  movzx   r9d, word ptr [rcx]
0x14000c87c  test    r9w, r9w
0x14000c880  jz      short loc_14000C897
0x14000c882  mov     [r8], r9w
0x14000c886  add     rcx, 2
0x14000c88a  add     r8, 2
0x14000c88e  dec     rax
0x14000c891  sub     rdx, 1
0x14000c895  jnz     short loc_14000C873
0x14000c897  mov     rax, rdx
0x14000c89a  lea     rcx, [r8-2]
0x14000c89e  neg     rax
0x14000c8a1  sbb     ebx, ebx
0x14000c8a3  not     ebx
0x14000c8a5  and     ebx, 80000005h
0x14000c8ab  test    rdx, rdx
0x14000c8ae  cmovnz  rcx, r8
0x14000c8b2  mov     [rcx], r10w
0x14000c8b6  jnz     short loc_14000C8C4
0x14000c8b8  mov     r9d, ebx
0x14000c8bb  lea     r8, aWerkernelhostR_5; "WERKERNELHOST:  RtlStringCchCopyW faile"...
0x14000c8c2  jmp     short loc_14000C8DC
0x14000c8c4  mov     rcx, rsi
0x14000c8c7  call    WerpCreateReportId
0x14000c8cc  mov     ebx, eax
0x14000c8ce  test    eax, eax
0x14000c8d0  jns     short loc_14000C8F5
0x14000c8d2  lea     r8, aWerkernelhostC_10; "WERKERNELHOST: Could not create report "...
0x14000c8d9  mov     r9d, eax
0x14000c8dc  mov     edx, 1; Level
0x14000c8e1  mov     ecx, r15d; ComponentId
0x14000c8e4  call    cs:__imp_DbgPrintEx
0x14000c8eb  nop     dword ptr [rax+rax+00h]
0x14000c8f0  jmp     loc_14000C854
0x14000c8f5  lea     rcx, [rsp+120h+var_DC]
0x14000c8fa  mov     rdx, r13
0x14000c8fd  mov     qword ptr [rsp+120h+var_100], rcx
0x14000c902  lea     r9, [rsi+10h]
0x14000c906  mov     ecx, [rsp+120h+var_E0]
0x14000c90a  lea     r8, [rsi+38h]
0x14000c90e  call    WerpCreateReport
0x14000c913  mov     ebx, eax
0x14000c915  xor     eax, eax
0x14000c917  test    ebx, ebx
0x14000c919  js      short loc_14000C921
0x14000c91b  cmp     [rsi+10h], rax
0x14000c91f  jnz     short loc_14000C977
0x14000c921  mov     r9d, ebx
0x14000c924  lea     r8, aWerkernelhostW_46; "WERKERNELHOST: WerKernelCreateReport fa"...
0x14000c92b  mov     edx, 1; Level
0x14000c930  mov     ecx, r15d; ComponentId
0x14000c933  call    cs:__imp_DbgPrintEx
0x14000c93a  nop     dword ptr [rax+rax+00h]
0x14000c93f  xor     ecx, ecx
0x14000c941  test    ebx, ebx
0x14000c943  jns     short loc_14000C977
0x14000c945  mov     [rdi], ecx
0x14000c947  mov     rcx, [rsi+10h]; KeyHandle
0x14000c94b  xor     edi, edi
0x14000c94d  test    rcx, rcx
0x14000c950  jz      short loc_14000C964
0x14000c952  call    WerpCancelReport
0x14000c957  mov     rcx, [rsi+10h]
0x14000c95b  call    WerpCloseHandle
0x14000c960  mov     [rsi+10h], rdi
0x14000c964  xor     edx, edx; Tag
0x14000c966  mov     rcx, rsi; P
0x14000c969  call    cs:__imp_ExFreePoolWithTag
0x14000c970  nop     dword ptr [rax+rax+00h]
0x14000c975  jmp     short loc_14000C9A5
0x14000c977  mov     eax, [rsi+4]
0x14000c97a  lea     r8, aWerkernelhostW_6; "WERKERNELHOST: WerLiveKernelCreateRepor"...
0x14000c981  mov     r9, rsi
0x14000c984  mov     [rsp+120h+var_100], eax
0x14000c988  mov     edx, 3; Level
0x14000c98d  mov     ecx, r15d; ComponentId
0x14000c990  call    cs:__imp_DbgPrintEx
0x14000c997  nop     dword ptr [rax+rax+00h]
0x14000c99c  mov     [r12], rsi
0x14000c9a0  mov     eax, [rsi+4]
0x14000c9a3  mov     [rdi], eax
0x14000c9a5  mov     r13d, [rsp+120h+var_DC]
0x14000c9aa  xor     edx, edx
0x14000c9ac  mov     rsi, [rbp+57h+SourceString]
0x14000c9b0  mov     eax, cs:dword_140009048
0x14000c9b6  cmp     eax, r15d
0x14000c9b9  jbe     loc_14000CAA0
0x14000c9bf  mov     rcx, cs:qword_140009060; int
0x14000c9c6  mov     r8, 400000000000h
0x14000c9d0  mov     rax, cs:qword_140009058
0x14000c9d7  test    r8, rax
0x14000c9da  jz      loc_14000CAA0
0x14000c9e0  mov     rax, rcx
0x14000c9e3  and     rax, r8
0x14000c9e6  cmp     rax, rcx
0x14000c9e9  jnz     loc_14000CAA0
0x14000c9ef  lea     rax, [rbp+57h+var_C8]
0x14000c9f3  mov     [rbp+57h+var_C8], 3000000h
0x14000c9fb  mov     r8d, 8; int
0x14000ca01  mov     [rbp+57h+var_A0], rax
0x14000ca05  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000ca09  mov     [rbp+57h+var_98], r8
0x14000ca0d  inc     rax
0x14000ca10  cmp     [rsi+rax*2], dx
0x14000ca14  jnz     short loc_14000CA0D
0x14000ca16  mov     edi, [rsp+120h+var_E0]
0x14000ca1a  lea     eax, ds:2[rax*2]
0x14000ca21  mov     r12d, [rsp+120h+var_D8]
0x14000ca26  mov     [rbp+57h+var_88], eax
0x14000ca29  lea     rax, [rsp+120h+var_D8]
0x14000ca2e  mov     [rbp+57h+var_80], rax
0x14000ca32  lea     rax, [rsp+120h+var_DC]
0x14000ca37  mov     [rbp+57h+var_70], rax
0x14000ca3b  lea     rax, [rsp+120h+var_E0]
0x14000ca40  mov     [rbp+57h+var_60], rax
0x14000ca44  lea     rax, [rbp+57h+SourceString]
0x14000ca48  mov     [rbp+57h+var_50], rax
0x14000ca4c  lea     rax, [rbp+57h+var_C0]
0x14000ca50  mov     [rbp+57h+var_84], edx
0x14000ca53  lea     rdx, byte_140008011; int
0x14000ca5a  mov     [rsp+120h+var_F8], rax; __int64
0x14000ca5f  mov     [rsp+120h+var_100], r8d; ULONG
0x14000ca64  mov     [rbp+57h+var_90], rsi
0x14000ca68  mov     [rsp+120h+var_D8], r12d
0x14000ca6d  mov     [rbp+57h+var_78], 4
0x14000ca75  mov     [rsp+120h+var_DC], edi
0x14000ca79  mov     [rbp+57h+var_68], 4
0x14000ca81  mov     [rsp+120h+var_E0], ebx
0x14000ca85  mov     [rbp+57h+var_58], 4
0x14000ca8d  mov     dword ptr [rbp+57h+SourceString], r13d
0x14000ca91  mov     [rbp+57h+var_48], 4
0x14000ca99  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ca9e  jmp     short loc_14000CAA9
0x14000caa0  mov     r12d, [rsp+120h+var_D8]
0x14000caa5  mov     edi, [rsp+120h+var_E0]
0x14000caa9  test    cs:Microsoft_Windows_WerKernelEnableBits, 1
0x14000cab0  jz      short loc_14000CAEC
0x14000cab2  mov     [rsp+120h+var_F0], r13d
0x14000cab7  mov     r9d, r12d
0x14000caba  mov     dword ptr [rsp+120h+var_F8], ebx
0x14000cabe  mov     r8, rsi
0x14000cac1  mov     [rsp+120h+var_100], edi
0x14000cac5  call    McTemplateU0zqqqq_EtwWriteTransfer
0x14000caca  test    eax, eax
0x14000cacc  jns     short loc_14000CAEC
0x14000cace  mov     r9d, eax
0x14000cad1  lea     r8, aWerkernelhostE; "WERKERNELHOST: EtwWrite failed with 0x%"...
0x14000cad8  mov     edx, 1; Level
0x14000cadd  mov     ecx, r15d; ComponentId
0x14000cae0  call    cs:__imp_DbgPrintEx
0x14000cae7  nop     dword ptr [rax+rax+00h]
0x14000caec  mov     eax, ebx
0x14000caee  jmp     short loc_14000CB1F
0x14000caf0  test    r12, r12
0x14000caf3  jz      short loc_14000CAF8
0x14000caf5  mov     [r8], rdx
0x14000caf8  test    rdi, rdi
0x14000cafb  jz      short loc_14000CAFF
0x14000cafd  mov     [rdi], edx
0x14000caff  mov     edx, 1; Level
0x14000cb04  lea     r8, aWerkernelhostW_48; "WERKERNELHOST: WerLiveKernelCreateRepor"...
0x14000cb0b  lea     ecx, [rdx+4]; ComponentId
0x14000cb0e  call    cs:__imp_DbgPrintEx
0x14000cb15  nop     dword ptr [rax+rax+00h]
0x14000cb1a  mov     eax, 0C000000Dh
0x14000cb1f  mov     rcx, [rbp+57h+var_40]
0x14000cb23  xor     rcx, rsp; StackCookie
0x14000cb26  call    __security_check_cookie
0x14000cb2b  add     rsp, 0F0h
0x14000cb32  pop     r15
0x14000cb34  pop     r13
0x14000cb36  pop     r12
0x14000cb38  pop     rdi
0x14000cb39  pop     rsi
0x14000cb3a  pop     rbx
0x14000cb3b  pop     rbp
0x14000cb3c  retn
```
