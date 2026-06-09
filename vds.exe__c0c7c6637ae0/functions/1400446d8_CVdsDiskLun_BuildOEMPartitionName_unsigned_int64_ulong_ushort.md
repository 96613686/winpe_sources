# CVdsDiskLun::BuildOEMPartitionName(unsigned __int64,ulong,ushort *)

- ea: `0x1400446d8`
- end: `0x140044ab3`
- name: `?BuildOEMPartitionName@CVdsDiskLun@@AEAAJ_KKPEAG@Z`
- size: `987`
- prototype: `__int64 __fastcall(CVdsDiskLun *this, __int64, __int64, unsigned __int16 *)`
- caller_count: `7`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x140020260`
- `0x140020bb0`
- `0x1400210b0`
- `0x140021b50`
- `0x140029600`
- `0x140029a70`
- `0x140045df0`

## callees

- `0x1400069e8`
- `0x14002e123`
- `0x14003ce10`
- `0x1400446d8`
- `0x140052e46`
- `0x140052e52`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004479e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400447b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400447cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400447e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044898`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044a43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044a5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004479e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400447b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400447cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400447e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044898`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044a43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044a5c`
- `vdsutil!VdsTraceEx` at `0x14004478a`
- `vdsutil!VdsTraceEx` at `0x140044809`
- `vdsutil!VdsTraceEx` at `0x140044a34`
- `vdsutil!VdsTraceEx` at `0x140044a81`
- `vdsutil!VdsTraceEx` at `0x14004478a`
- `vdsutil!VdsTraceEx` at `0x140044809`
- `vdsutil!VdsTraceEx` at `0x140044a34`
- `vdsutil!VdsTraceEx` at `0x140044a81`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004473e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004473e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400449eb`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140044a8d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400449eb`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140044a8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsDiskLun::BuildOEMPartitionName(CVdsDiskLun *this, __int64 a2, __int64 a3, unsigned __int16 *a4)
{
  unsigned int v7; // ebx
  const char *v8; // r8
  wchar_t *v9; // rdi
  size_t *v10; // r8
  int v11; // eax
  __int64 v12; // rdx
  const char *v13; // r8
  size_t cchToCopy; // [rsp+20h] [rbp-E0h]
  _BYTE v16[16]; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v17[8]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v18; // [rsp+60h] [rbp-A0h]
  _BYTE Buf1[96]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v20[16]; // [rsp+D0h] [rbp-30h] BYREF
  int v21; // [rsp+E0h] [rbp-20h]
  int v22; // [rsp+ECh] [rbp-14h]
  int v23; // [rsp+F0h] [rbp-10h]
  LPVOID pv; // [rsp+128h] [rbp+28h]
  wchar_t *String1; // [rsp+130h] [rbp+30h]
  LPVOID v26; // [rsp+138h] [rbp+38h]
  LPVOID v27; // [rsp+140h] [rbp+40h]
  LPVOID v28; // [rsp+148h] [rbp+48h]
  wchar_t pszDest[8]; // [rsp+150h] [rbp+50h] BYREF

  memset_0(v20, 0, 0x80u);
  memset_0(v17, 0, 0x90u);
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v16, 0x5Eu, "CVdsDiskLun::BuildOEMPartitionName()");
  if ( a4 )
  {
    *a4 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 28) + 24LL))(*((_QWORD *)this + 28), v20);
    if ( (v7 & 0x80000000) != 0 )
    {
      v8 = "CVdsDiskLun::BuildOEMPartitionName, 2, hr=%lX";
      goto LABEL_5;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    if ( v26 )
    {
      CoTaskMemFree(v26);
      v26 = 0;
    }
    if ( v27 )
    {
      CoTaskMemFree(v27);
      v27 = 0;
    }
    if ( v28 )
    {
      CoTaskMemFree(v28);
      v28 = 0;
    }
    if ( v21 == 6 )
    {
      VdsTraceEx(94, 1, "CVdsDiskLun::BuildOEMPartitionName, 3, hr=%lX", v7);
      if ( String1 )
      {
        CoTaskMemFree(String1);
        String1 = 0;
      }
      v7 = -2147212204;
      goto LABEL_50;
    }
    if ( v22 != 7 || v23 != 12 )
    {
      if ( String1 )
      {
        CoTaskMemFree(String1);
        String1 = 0;
      }
      v7 = -2147211942;
      v13 = "CVdsDiskLun::BuildOEMPartitionName, 4, hr=%lX";
      goto LABEL_49;
    }
    v9 = String1;
    if ( String1 )
    {
      if ( !wcsncmp_0(String1, L"\\\\?\\PhysicalDrive", 0x11u) )
      {
        StringCopyWorkerW(pszDest, 5u, v10, v9 + 17, 4u);
        pszDest[4] = 0;
        if ( String1 )
        {
          CoTaskMemFree(String1);
          String1 = 0;
        }
        v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _DWORD *))(**((_QWORD **)this + 30) + 24LL))(
                *((_QWORD *)this + 30),
                a2,
                v17);
        v7 = v11;
        if ( v11 < 0 )
        {
          VdsTraceEx(94, 0, "CVdsDiskLun::BuildOEMPartitionName, 6, %lX", (unsigned int)v11);
          goto LABEL_50;
        }
        if ( v17[0] == 1 )
        {
          if ( v18 <= 0x2Du && (v12 = 0x3F000000D8F2LL, _bittest64(&v12, v18)) || v18 == 0xEF )
          {
            v13 = "CVdsDiskLun::BuildOEMPartitionName, 7, %lX";
LABEL_31:
            v7 = -2147211921;
LABEL_49:
            VdsTraceEx(94, 1, v13, v7);
            goto LABEL_50;
          }
        }
        else
        {
          if ( v17[0] != 2 )
          {
            v7 = -2147211932;
            VdsTraceEx(94, 1, "CVdsDiskLun::BuildOEMPartitionName, 9, %lX", 2147755364LL);
            goto LABEL_50;
          }
          if ( !memcmp_0(Buf1, &PARTITION_BASIC_DATA_GUID, 0x10u) && (Buf1[16] & 1) == 0
            || !memcmp_0(Buf1, &PARTITION_MSFT_RESERVED_GUID, 0x10u)
            || !memcmp_0(Buf1, &PARTITION_LDM_METADATA_GUID, 0x10u)
            || !memcmp_0(Buf1, &PARTITION_LDM_DATA_GUID, 0x10u)
            || !memcmp_0(Buf1, &PARTITION_CLUSTER_GUID, 0x10u)
            || !memcmp_0(Buf1, &PARTITION_ENTRY_UNUSED_GUID, 0x10u) )
          {
            v13 = "CVdsDiskLun::BuildOEMPartitionName, 8, %lX";
            goto LABEL_31;
          }
        }
        LODWORD(cchToCopy) = v17[2];
        StringCchPrintfW(a4, 0x28u, L"\\Device\\Harddisk%s\\Partition%d", pszDest, cchToCopy);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
        return 0;
      }
    }
    else
    {
      v9 = L"UNKNOWN";
    }
    v7 = -2147212223;
    VdsTraceEx(94, 0, "CVdsDiskLun::BuildOEMPartitionName, 5, %S, hr=%lX", v9, -2147212223);
    if ( String1 )
    {
      CoTaskMemFree(String1);
      String1 = 0;
    }
    goto LABEL_50;
  }
  v7 = -2147024809;
  v8 = "CVdsDiskLun::BuildOEMPartitionName, 1, hr=%lX";
LABEL_5:
  VdsTraceEx(94, 0, v8, v7);
LABEL_50:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
  return v7;
}

```

## disassembly

```asm
0x1400446d8  push    rbp
0x1400446da  push    rbx
0x1400446db  push    rsi
0x1400446dc  push    rdi
0x1400446dd  push    r13
0x1400446df  push    r14
0x1400446e1  push    r15
0x1400446e3  lea     rbp, [rsp-70h]
0x1400446e8  sub     rsp, 170h
0x1400446ef  mov     rax, cs:__security_cookie
0x1400446f6  xor     rax, rsp
0x1400446f9  mov     [rbp+0A0h+var_40], rax
0x1400446fd  mov     r14, r9
0x140044700  mov     r15, rdx
0x140044703  mov     rsi, rcx
0x140044706  xor     edx, edx; Val
0x140044708  mov     r8d, 80h; Size
0x14004470e  lea     rcx, [rbp+0A0h+var_D0]; void *
0x140044712  call    memset_0
0x140044717  xor     edx, edx; Val
0x140044719  mov     r8d, 90h; Size
0x14004471f  lea     rcx, [rsp+1A0h+var_160]; void *
0x140044724  call    memset_0
0x140044729  lea     r8, aCvdsdisklunBui_1; "CVdsDiskLun::BuildOEMPartitionName()"
0x140044730  mov     r13d, 5Eh ; '^'
0x140044736  mov     edx, r13d
0x140044739  lea     rcx, [rsp+1A0h+var_170]
0x14004473e  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140044744  nop
0x140044745  test    r14, r14
0x140044748  jnz     short loc_140044758
0x14004474a  mov     ebx, 80070057h
0x14004474f  lea     r8, aCvdsdisklunBui_8; "CVdsDiskLun::BuildOEMPartitionName, 1, "...
0x140044756  jmp     short loc_140044782
0x140044758  xor     eax, eax
0x14004475a  mov     [r14], ax
0x14004475e  mov     rcx, [rsi+0E0h]
0x140044765  mov     rax, [rcx]
0x140044768  lea     rdx, [rbp+0A0h+var_D0]
0x14004476c  mov     rax, [rax+18h]
0x140044770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044775  mov     ebx, eax
0x140044777  test    eax, eax
0x140044779  jns     short loc_140044795
0x14004477b  lea     r8, aCvdsdisklunBui_0; "CVdsDiskLun::BuildOEMPartitionName, 2, "...
0x140044782  mov     r9d, ebx
0x140044785  xor     edx, edx
0x140044787  mov     ecx, r13d
0x14004478a  call    cs:__imp_VdsTraceEx
0x140044790  jmp     loc_140044A88
0x140044795  mov     rcx, [rbp+0A0h+pv]; pv
0x140044799  test    rcx, rcx
0x14004479c  jz      short loc_1400447AC
0x14004479e  call    cs:__imp_CoTaskMemFree
0x1400447a4  mov     [rbp+0A0h+pv], 0
0x1400447ac  mov     rcx, [rbp+0A0h+var_68]; pv
0x1400447b0  test    rcx, rcx
0x1400447b3  jz      short loc_1400447C3
0x1400447b5  call    cs:__imp_CoTaskMemFree
0x1400447bb  mov     [rbp+0A0h+var_68], 0
0x1400447c3  mov     rcx, [rbp+0A0h+var_60]; pv
0x1400447c7  test    rcx, rcx
0x1400447ca  jz      short loc_1400447DA
0x1400447cc  call    cs:__imp_CoTaskMemFree
0x1400447d2  mov     [rbp+0A0h+var_60], 0
0x1400447da  mov     rcx, [rbp+0A0h+var_58]; pv
0x1400447de  test    rcx, rcx
0x1400447e1  jz      short loc_1400447F1
0x1400447e3  call    cs:__imp_CoTaskMemFree
0x1400447e9  mov     [rbp+0A0h+var_58], 0
0x1400447f1  cmp     [rbp+0A0h+var_C0], 6
0x1400447f5  jnz     short loc_140044830
0x1400447f7  mov     r9d, ebx
0x1400447fa  lea     r8, aCvdsdisklunBui_6; "CVdsDiskLun::BuildOEMPartitionName, 3, "...
0x140044801  mov     edx, 1
0x140044806  mov     ecx, r13d
0x140044809  call    cs:__imp_VdsTraceEx
0x14004480f  mov     rcx, [rbp+0A0h+String1]; pv
0x140044813  test    rcx, rcx
0x140044816  jz      short loc_140044826
0x140044818  call    cs:__imp_CoTaskMemFree
0x14004481e  mov     [rbp+0A0h+String1], 0
0x140044826  mov     ebx, 80042454h
0x14004482b  jmp     loc_140044A88
0x140044830  cmp     [rbp+0A0h+var_B4], 7
0x140044834  jnz     loc_140044A53
0x14004483a  cmp     [rbp+0A0h+var_B0], 0Ch
0x14004483e  jnz     loc_140044A53
0x140044844  mov     rdi, [rbp+0A0h+String1]
0x140044848  test    rdi, rdi
0x14004484b  jz      loc_140044A15
0x140044851  mov     r8d, 11h; MaxCount
0x140044857  lea     rdx, aPhysicaldrive; "\\\\?\\PhysicalDrive"
0x14004485e  mov     rcx, rdi; String1
0x140044861  call    wcsncmp_0
0x140044866  test    eax, eax
0x140044868  jnz     loc_140044A1C
0x14004486e  lea     r9, [rdi+22h]; pszSrc
0x140044872  mov     [rsp+1A0h+cchToCopy], 4; cchToCopy
0x14004487b  lea     edx, [rax+5]; cchDest
0x14004487e  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x140044882  call    StringCopyWorkerW
0x140044887  xor     r11d, r11d
0x14004488a  mov     [rbp+0A0h+var_48], r11w
0x14004488f  mov     rcx, [rbp+0A0h+String1]; pv
0x140044893  test    rcx, rcx
0x140044896  jz      short loc_1400448A6
0x140044898  call    cs:__imp_CoTaskMemFree
0x14004489e  mov     [rbp+0A0h+String1], 0
0x1400448a6  mov     rcx, [rsi+0F0h]
0x1400448ad  mov     rax, [rcx]
0x1400448b0  lea     r8, [rsp+1A0h+var_160]
0x1400448b5  mov     rdx, r15
0x1400448b8  mov     rax, [rax+18h]
0x1400448bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400448c1  mov     ebx, eax
0x1400448c3  test    eax, eax
0x1400448c5  jns     short loc_1400448D6
0x1400448c7  mov     r9d, eax
0x1400448ca  lea     r8, aCvdsdisklunBui_7; "CVdsDiskLun::BuildOEMPartitionName, 6, "...
0x1400448d1  jmp     loc_140044785
0x1400448d6  mov     edi, 1
0x1400448db  cmp     [rsp+1A0h+var_160], edi
0x1400448df  jnz     short loc_140044917
0x1400448e1  movzx   ecx, [rsp+1A0h+var_140]
0x1400448e6  cmp     cl, 2Dh ; '-'
0x1400448e9  ja      short loc_1400448FB
0x1400448eb  mov     rdx, 3F000000D8F2h
0x1400448f5  bt      rdx, rcx
0x1400448f9  jb      short loc_140044904
0x1400448fb  cmp     cl, 0EFh
0x1400448fe  jnz     loc_1400449C5
0x140044904  lea     r8, aCvdsdisklunBui; "CVdsDiskLun::BuildOEMPartitionName, 7, "...
0x14004490b  mov     ebx, 8004256Fh
0x140044910  mov     edx, edi
0x140044912  jmp     loc_140044A7B
0x140044917  cmp     [rsp+1A0h+var_160], 2
0x14004491c  jnz     loc_140044A04
0x140044922  mov     ebx, 10h
0x140044927  mov     r8d, ebx; Size
0x14004492a  lea     rdx, PARTITION_BASIC_DATA_GUID; Buf2
0x140044931  lea     rcx, [rsp+1A0h+Buf1]; Buf1
0x140044936  call    memcmp_0
0x14004493b  test    eax, eax
0x14004493d  jnz     short loc_140044949
0x14004493f  test    [rbp+0A0h+var_120], dil
0x140044943  jz      loc_1400449F8
0x140044949  mov     r8, rbx; Size
0x14004494c  lea     rdx, PARTITION_MSFT_RESERVED_GUID; Buf2
0x140044953  lea     rcx, [rsp+1A0h+Buf1]; Buf1
0x140044958  call    memcmp_0
0x14004495d  test    eax, eax
0x14004495f  jz      loc_1400449F8
0x140044965  mov     r8, rbx; Size
0x140044968  lea     rdx, PARTITION_LDM_METADATA_GUID; Buf2
0x14004496f  lea     rcx, [rsp+1A0h+Buf1]; Buf1
0x140044974  call    memcmp_0
0x140044979  test    eax, eax
0x14004497b  jz      short loc_1400449F8
0x14004497d  mov     r8, rbx; Size
0x140044980  lea     rdx, PARTITION_LDM_DATA_GUID; Buf2
0x140044987  lea     rcx, [rsp+1A0h+Buf1]; Buf1
0x14004498c  call    memcmp_0
0x140044991  test    eax, eax
0x140044993  jz      short loc_1400449F8
0x140044995  mov     r8, rbx; Size
0x140044998  lea     rdx, PARTITION_CLUSTER_GUID; Buf2
0x14004499f  lea     rcx, [rsp+1A0h+Buf1]; Buf1
0x1400449a4  call    memcmp_0
0x1400449a9  test    eax, eax
0x1400449ab  jz      short loc_1400449F8
0x1400449ad  mov     r8, rbx; Size
0x1400449b0  lea     rdx, PARTITION_ENTRY_UNUSED_GUID; Buf2
0x1400449b7  lea     rcx, [rsp+1A0h+Buf1]; Buf1
0x1400449bc  call    memcmp_0
0x1400449c1  test    eax, eax
0x1400449c3  jz      short loc_1400449F8
0x1400449c5  mov     eax, [rsp+1A0h+var_158]
0x1400449c9  mov     dword ptr [rsp+1A0h+cchToCopy], eax
0x1400449cd  lea     r9, [rbp+0A0h+pszDest]
0x1400449d1  lea     r8, aDeviceHarddisk_1; "\\Device\\Harddisk%s\\Partition%d"
0x1400449d8  mov     edx, 28h ; '('; unsigned __int64
0x1400449dd  mov     rcx, r14; unsigned __int16 *
0x1400449e0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400449e5  nop
0x1400449e6  lea     rcx, [rsp+1A0h+var_170]
0x1400449eb  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400449f1  xor     eax, eax
0x1400449f3  jmp     loc_140044A95
0x1400449f8  lea     r8, aCvdsdisklunBui_3; "CVdsDiskLun::BuildOEMPartitionName, 8, "...
0x1400449ff  jmp     loc_14004490B
0x140044a04  mov     ebx, 80042564h
0x140044a09  lea     r8, aCvdsdisklunBui_5; "CVdsDiskLun::BuildOEMPartitionName, 9, "...
0x140044a10  jmp     loc_140044910
0x140044a15  lea     rdi, aUnknown_0; "UNKNOWN"
0x140044a1c  mov     ebx, 80042441h
0x140044a21  mov     dword ptr [rsp+1A0h+cchToCopy], ebx
0x140044a25  mov     r9, rdi
0x140044a28  lea     r8, aCvdsdisklunBui_4; "CVdsDiskLun::BuildOEMPartitionName, 5, "...
0x140044a2f  xor     edx, edx
0x140044a31  mov     ecx, r13d
0x140044a34  call    cs:__imp_VdsTraceEx
0x140044a3a  mov     rcx, [rbp+0A0h+String1]; pv
0x140044a3e  test    rcx, rcx
0x140044a41  jz      short loc_140044A88
0x140044a43  call    cs:__imp_CoTaskMemFree
0x140044a49  mov     [rbp+0A0h+String1], 0
0x140044a51  jmp     short loc_140044A88
0x140044a53  mov     rcx, [rbp+0A0h+String1]; pv
0x140044a57  test    rcx, rcx
0x140044a5a  jz      short loc_140044A6A
0x140044a5c  call    cs:__imp_CoTaskMemFree
0x140044a62  mov     [rbp+0A0h+String1], 0
0x140044a6a  mov     ebx, 8004255Ah
0x140044a6f  lea     r8, aCvdsdisklunBui_2; "CVdsDiskLun::BuildOEMPartitionName, 4, "...
0x140044a76  mov     edx, 1
0x140044a7b  mov     r9d, ebx
0x140044a7e  mov     ecx, r13d
0x140044a81  call    cs:__imp_VdsTraceEx
0x140044a87  nop
0x140044a88  lea     rcx, [rsp+1A0h+var_170]
0x140044a8d  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140044a93  mov     eax, ebx
0x140044a95  mov     rcx, [rbp+0A0h+var_40]
0x140044a99  xor     rcx, rsp; StackCookie
0x140044a9c  call    __security_check_cookie
0x140044aa1  add     rsp, 170h
0x140044aa8  pop     r15
0x140044aaa  pop     r14
0x140044aac  pop     r13
0x140044aae  pop     rdi
0x140044aaf  pop     rsi
0x140044ab0  pop     rbx
0x140044ab1  pop     rbp
0x140044ab2  retn
```
