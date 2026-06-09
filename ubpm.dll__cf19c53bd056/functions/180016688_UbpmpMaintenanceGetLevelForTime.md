# UbpmpMaintenanceGetLevelForTime

- ea: `0x180016688`
- end: `0x1800169cb`
- name: `UbpmpMaintenanceGetLevelForTime`
- size: `835`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014840`

## callees

- `0x180016688`
- `0x18003488c`
- `0x18003d810`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016733`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016747`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001675e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800167d1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800168a1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800168b2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800168c3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800168eb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800168fc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016935`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001694e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001695f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016970`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016981`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016996`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016733`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016747`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001675e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800167d1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800168a1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800168b2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800168c3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800168eb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800168fc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016935`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001694e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001695f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016970`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016981`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016996`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001671f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800167be`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180016846`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001687d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001671f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800167be`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180016846`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001687d`

## pseudocode

```c
FILETIME *__fastcall UbpmpMaintenanceGetLevelForTime(
        __int64 a1,
        __int64 a2,
        const FILETIME *a3,
        const FILETIME *a4,
        FILETIME *a5,
        FILETIME *lpFileTime2,
        __int64 a7,
        char a8,
        char *a9,
        FILETIME *a10)
{
  FILETIME v14; // rbx
  FILETIME v15; // rbx
  FILETIME v16; // rdi
  char v17; // di
  FILETIME *result; // rax
  FILETIME v19; // rdi
  FILETIME FileTime; // [rsp+20h] [rbp-50h] BYREF
  FILETIME v21; // [rsp+28h] [rbp-48h] BYREF
  FILETIME FileTime1; // [rsp+30h] [rbp-40h] BYREF
  FILETIME FileTime2; // [rsp+38h] [rbp-38h] BYREF
  char *v24; // [rsp+40h] [rbp-30h]
  FILETIME *v25; // [rsp+48h] [rbp-28h]
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-20h] BYREF

  v24 = a9;
  v25 = a10;
  v21 = *a4;
  FileTime2 = v21;
  v14 = (FILETIME)(*(_QWORD *)&v21 + 864000000000LL);
  SystemTime = 0;
  if ( *(_QWORD *)&v21 + 864000000000LL >= *(unsigned __int64 *)&v21 )
  {
    *(_QWORD *)&v21 += 864000000000LL;
    FileTime = v14;
    if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
      FileTime2 = v14;
  }
  if ( CompareFileTime(a3, lpFileTime2) < 0 )
    *lpFileTime2 = *a3;
  if ( CompareFileTime(lpFileTime2, a4) < 0 )
    *lpFileTime2 = *a4;
  if ( CompareFileTime(lpFileTime2, a5) < 0 )
    *lpFileTime2 = *a5;
  v15 = *a3;
  FileTime1 = *lpFileTime2;
  v21 = FileTime1;
  FileTime = v15;
  SystemTime = 0;
  if ( *(_QWORD *)&FileTime + 864000000000LL >= *(unsigned __int64 *)&FileTime )
  {
    FileTime = (FILETIME)(*(_QWORD *)&v15 + 864000000000LL);
    if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
      *(_QWORD *)&v15 += 864000000000LL;
  }
  if ( CompareFileTime(a3, &FileTime2) < 0 )
  {
    v17 = 0;
    goto LABEL_16;
  }
  SystemTime = 0;
  v16 = (FILETIME)(*(_QWORD *)&FileTime1 + a1);
  if ( *(_QWORD *)&FileTime1 + a1 < *(unsigned __int64 *)&FileTime1
    || (FileTime = (FILETIME)(*(_QWORD *)&FileTime1 + a1), !FileTimeToSystemTime(&FileTime, &SystemTime))
    || (FileTime1 = v16,
        SystemTime = 0,
        v19 = (FILETIME)(*(_QWORD *)&v21 + a2),
        *(_QWORD *)&v21 + a2 < *(unsigned __int64 *)&v21)
    || (FileTime = (FILETIME)(*(_QWORD *)&v21 + a2), !FileTimeToSystemTime(&FileTime, &SystemTime)) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v17 = 2;
LABEL_16:
    v15 = FileTime2;
    goto LABEL_17;
  }
  v21 = v19;
  if ( !a2 )
  {
    if ( !CompareFileTime(&FileTime1, a3) || CompareFileTime(&FileTime1, a3) < 0 )
      goto LABEL_27;
    goto LABEL_31;
  }
  if ( a8 )
  {
    if ( !CompareFileTime(&v21, a3) || CompareFileTime(&v21, a3) < 0 )
    {
      v17 = 4;
      goto LABEL_17;
    }
    if ( (!CompareFileTime(&FileTime1, a3) || CompareFileTime(&FileTime1, a3) < 0) && CompareFileTime(a3, &v21) < 0 )
    {
      v15 = v21;
      v17 = 3;
      goto LABEL_17;
    }
  }
  if ( CompareFileTime(&FileTime1, a3) && CompareFileTime(&FileTime1, a3) >= 0 )
  {
    if ( CompareFileTime(a3, &FileTime1) >= 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_27:
      v17 = 2;
      goto LABEL_17;
    }
LABEL_31:
    v15 = FileTime1;
    v17 = 0;
    goto LABEL_17;
  }
  *(FILETIME *)&SystemTime.wYear = v21;
  v17 = 2;
  FileTime = v15;
  if ( CompareFileTime((const FILETIME *)&SystemTime, &FileTime) > 0 )
    v15 = v21;
LABEL_17:
  *v24 = v17;
  result = v25;
  *v25 = v15;
  return result;
}

```

## disassembly

```asm
0x180016688  mov     [rsp-38h+arg_0], rbx
0x18001668d  push    rbp
0x18001668e  push    rsi
0x18001668f  push    rdi
0x180016690  push    r12
0x180016692  push    r13
0x180016694  push    r14
0x180016696  push    r15
0x180016698  mov     rbp, rsp
0x18001669b  sub     rsp, 70h
0x18001669f  mov     rax, cs:__security_cookie
0x1800166a6  xor     rax, rsp
0x1800166a9  mov     [rbp+var_10], rax
0x1800166ad  mov     rax, [rbp+arg_40]
0x1800166b4  mov     rbx, 0C92A69C000h
0x1800166be  mov     r13, [rbp+arg_20]
0x1800166c2  xorps   xmm0, xmm0
0x1800166c5  mov     rdi, [rbp+lpFileTime2]
0x1800166c9  mov     r12, r9
0x1800166cc  mov     [rbp+var_30], rax
0x1800166d0  mov     r15, r8
0x1800166d3  mov     rax, [rbp+arg_48]
0x1800166da  mov     rsi, rdx
0x1800166dd  mov     [rbp+var_28], rax
0x1800166e1  mov     r14, rcx
0x1800166e4  mov     rax, [r9]
0x1800166e7  mov     [rbp+var_48.dwLowDateTime], eax
0x1800166ea  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x1800166ee  shr     rax, 20h
0x1800166f2  mov     [rbp+var_48.dwHighDateTime], eax
0x1800166f5  add     rbx, qword ptr [rbp+var_48.dwLowDateTime]
0x1800166f9  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800166fd  cmp     rbx, qword ptr [rbp+var_48.dwLowDateTime]
0x180016701  jb      short loc_18001672D
0x180016703  mov     qword ptr [rbp+var_48.dwLowDateTime], rbx
0x180016707  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18001670b  mov     eax, [rbp+var_48.dwLowDateTime]
0x18001670e  lea     rcx, [rbp+FileTime]; lpFileTime
0x180016712  mov     [rbp+FileTime.dwLowDateTime], eax
0x180016715  mov     rax, rbx
0x180016718  shr     rax, 20h
0x18001671c  mov     [rbp+FileTime.dwHighDateTime], eax
0x18001671f  call    cs:__imp_FileTimeToSystemTime
0x180016725  test    eax, eax
0x180016727  jz      short loc_18001672D
0x180016729  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rbx
0x18001672d  mov     rdx, rdi; lpFileTime2
0x180016730  mov     rcx, r15; lpFileTime1
0x180016733  call    cs:__imp_CompareFileTime
0x180016739  test    eax, eax
0x18001673b  js      loc_1800169B8
0x180016741  mov     rdx, r12; lpFileTime2
0x180016744  mov     rcx, rdi; lpFileTime1
0x180016747  call    cs:__imp_CompareFileTime
0x18001674d  test    eax, eax
0x18001674f  jns     short loc_180016758
0x180016751  mov     rax, [r12]
0x180016755  mov     [rdi], rax
0x180016758  mov     rdx, r13; lpFileTime2
0x18001675b  mov     rcx, rdi; lpFileTime1
0x18001675e  call    cs:__imp_CompareFileTime
0x180016764  test    eax, eax
0x180016766  js      loc_180016912
0x18001676c  mov     rax, [rdi]
0x18001676f  xorps   xmm0, xmm0
0x180016772  mov     rbx, [r15]
0x180016775  mov     rdi, 0C92A69C000h
0x18001677f  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x180016783  mov     qword ptr [rbp+var_48.dwLowDateTime], rax
0x180016787  mov     rax, rbx
0x18001678a  shr     rax, 20h
0x18001678e  mov     [rbp+FileTime.dwHighDateTime], eax
0x180016791  mov     [rbp+FileTime.dwLowDateTime], ebx
0x180016794  add     rdi, qword ptr [rbp+FileTime.dwLowDateTime]
0x180016798  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18001679c  cmp     rdi, qword ptr [rbp+FileTime.dwLowDateTime]
0x1800167a0  jb      short loc_1800167CA
0x1800167a2  mov     qword ptr [rbp+FileTime.dwLowDateTime], rdi
0x1800167a6  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x1800167aa  mov     eax, [rbp+FileTime.dwLowDateTime]
0x1800167ad  lea     rcx, [rbp+FileTime]; lpFileTime
0x1800167b1  mov     [rbp+FileTime.dwLowDateTime], eax
0x1800167b4  mov     rax, rdi
0x1800167b7  shr     rax, 20h
0x1800167bb  mov     [rbp+FileTime.dwHighDateTime], eax
0x1800167be  call    cs:__imp_FileTimeToSystemTime
0x1800167c4  test    eax, eax
0x1800167c6  cmovnz  rbx, rdi
0x1800167ca  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x1800167ce  mov     rcx, r15; lpFileTime1
0x1800167d1  call    cs:__imp_CompareFileTime
0x1800167d7  test    eax, eax
0x1800167d9  js      loc_1800169C3
0x1800167df  mov     rax, qword ptr [rbp+FileTime1.dwLowDateTime]
0x1800167e3  xorps   xmm0, xmm0
0x1800167e6  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800167ea  lea     rdi, [rax+r14]
0x1800167ee  cmp     rdi, rax
0x1800167f1  jnb     short loc_180016831
0x1800167f3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800167f8  mov     dil, 2
0x1800167fb  mov     rbx, qword ptr [rbp+FileTime2.dwLowDateTime]
0x1800167ff  mov     rax, [rbp+var_30]
0x180016803  mov     [rax], dil
0x180016806  mov     rax, [rbp+var_28]
0x18001680a  mov     [rax], rbx
0x18001680d  mov     rcx, [rbp+var_10]
0x180016811  xor     rcx, rsp; StackCookie
0x180016814  call    __security_check_cookie
0x180016819  mov     rbx, [rsp+70h+arg_0]
0x180016821  add     rsp, 70h
0x180016825  pop     r15
0x180016827  pop     r14
0x180016829  pop     r13
0x18001682b  pop     r12
0x18001682d  pop     rdi
0x18001682e  pop     rsi
0x18001682f  pop     rbp
0x180016830  retn
0x180016831  mov     rax, rdi
0x180016834  mov     [rbp+FileTime.dwLowDateTime], edi
0x180016837  shr     rax, 20h
0x18001683b  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18001683f  lea     rcx, [rbp+FileTime]; lpFileTime
0x180016843  mov     [rbp+FileTime.dwHighDateTime], eax
0x180016846  call    cs:__imp_FileTimeToSystemTime
0x18001684c  test    eax, eax
0x18001684e  jz      short loc_1800167F3
0x180016850  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rdi
0x180016854  mov     rax, qword ptr [rbp+var_48.dwLowDateTime]
0x180016858  xorps   xmm0, xmm0
0x18001685b  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18001685f  lea     rdi, [rax+rsi]
0x180016863  cmp     rdi, rax
0x180016866  jb      short loc_1800168DA
0x180016868  mov     rax, rdi
0x18001686b  mov     [rbp+FileTime.dwLowDateTime], edi
0x18001686e  shr     rax, 20h
0x180016872  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180016876  lea     rcx, [rbp+FileTime]; lpFileTime
0x18001687a  mov     [rbp+FileTime.dwHighDateTime], eax
0x18001687d  call    cs:__imp_FileTimeToSystemTime
0x180016883  test    eax, eax
0x180016885  jz      short loc_1800168DA
0x180016887  mov     qword ptr [rbp+var_48.dwLowDateTime], rdi
0x18001688b  test    rsi, rsi
0x18001688e  jz      short loc_1800168E4
0x180016890  cmp     [rbp+arg_38], 0
0x180016894  jnz     loc_180016947
0x18001689a  mov     rdx, r15; lpFileTime2
0x18001689d  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800168a1  call    cs:__imp_CompareFileTime
0x1800168a7  test    eax, eax
0x1800168a9  jz      short loc_18001691E
0x1800168ab  mov     rdx, r15; lpFileTime2
0x1800168ae  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800168b2  call    cs:__imp_CompareFileTime
0x1800168b8  test    eax, eax
0x1800168ba  js      short loc_18001691E
0x1800168bc  lea     rdx, [rbp+FileTime1]; lpFileTime2
0x1800168c0  mov     rcx, r15; lpFileTime1
0x1800168c3  call    cs:__imp_CompareFileTime
0x1800168c9  test    eax, eax
0x1800168cb  js      short loc_180016906
0x1800168cd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800168d2  mov     dil, 2
0x1800168d5  jmp     loc_1800167FF
0x1800168da  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800168df  jmp     loc_1800167F8
0x1800168e4  mov     rdx, r15; lpFileTime2
0x1800168e7  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800168eb  call    cs:__imp_CompareFileTime
0x1800168f1  test    eax, eax
0x1800168f3  jz      short loc_1800168D2
0x1800168f5  mov     rdx, r15; lpFileTime2
0x1800168f8  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800168fc  call    cs:__imp_CompareFileTime
0x180016902  test    eax, eax
0x180016904  js      short loc_1800168D2
0x180016906  mov     rbx, qword ptr [rbp+FileTime1.dwLowDateTime]
0x18001690a  xor     dil, dil
0x18001690d  jmp     loc_1800167FF
0x180016912  mov     rax, [r13+0]
0x180016916  mov     [rdi], rax
0x180016919  jmp     loc_18001676C
0x18001691e  mov     rax, qword ptr [rbp+var_48.dwLowDateTime]
0x180016922  lea     rdx, [rbp+FileTime]; lpFileTime2
0x180016926  lea     rcx, [rbp+SystemTime]; lpFileTime1
0x18001692a  mov     qword ptr [rbp+SystemTime.wYear], rax
0x18001692e  mov     dil, 2
0x180016931  mov     qword ptr [rbp+FileTime.dwLowDateTime], rbx
0x180016935  call    cs:__imp_CompareFileTime
0x18001693b  test    eax, eax
0x18001693d  cmovg   rbx, qword ptr [rbp+var_48.dwLowDateTime]
0x180016942  jmp     loc_1800167FF
0x180016947  mov     rdx, r15; lpFileTime2
0x18001694a  lea     rcx, [rbp+var_48]; lpFileTime1
0x18001694e  call    cs:__imp_CompareFileTime
0x180016954  test    eax, eax
0x180016956  jz      short loc_1800169B0
0x180016958  mov     rdx, r15; lpFileTime2
0x18001695b  lea     rcx, [rbp+var_48]; lpFileTime1
0x18001695f  call    cs:__imp_CompareFileTime
0x180016965  test    eax, eax
0x180016967  js      short loc_1800169B0
0x180016969  mov     rdx, r15; lpFileTime2
0x18001696c  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180016970  call    cs:__imp_CompareFileTime
0x180016976  test    eax, eax
0x180016978  jz      short loc_18001698F
0x18001697a  mov     rdx, r15; lpFileTime2
0x18001697d  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180016981  call    cs:__imp_CompareFileTime
0x180016987  test    eax, eax
0x180016989  jns     loc_18001689A
0x18001698f  lea     rdx, [rbp+var_48]; lpFileTime2
0x180016993  mov     rcx, r15; lpFileTime1
0x180016996  call    cs:__imp_CompareFileTime
0x18001699c  test    eax, eax
0x18001699e  jns     loc_18001689A
0x1800169a4  mov     rbx, qword ptr [rbp+var_48.dwLowDateTime]
0x1800169a8  mov     dil, 3
0x1800169ab  jmp     loc_1800167FF
0x1800169b0  mov     dil, 4
0x1800169b3  jmp     loc_1800167FF
0x1800169b8  mov     rax, [r15]
0x1800169bb  mov     [rdi], rax
0x1800169be  jmp     loc_180016741
0x1800169c3  xor     dil, dil
0x1800169c6  jmp     loc_1800167FB
```
