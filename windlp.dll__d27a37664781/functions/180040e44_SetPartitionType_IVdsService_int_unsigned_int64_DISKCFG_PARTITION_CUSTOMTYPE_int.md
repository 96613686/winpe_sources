# SetPartitionType(IVdsService *,int,unsigned __int64,_DISKCFG_PARTITION_CUSTOMTYPE,int)

- ea: `0x180040e44`
- end: `0x180041191`
- name: `?SetPartitionType@@YAJPEAUIVdsService@@H_KU_DISKCFG_PARTITION_CUSTOMTYPE@@H@Z`
- size: `845`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003f9f8`

## callees

- `0x180039394`
- `0x180040e44`
- `0x1800417a8`
- `0x18007ec76`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800410c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800410db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800410ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041101`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041114`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800410c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800410db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800410ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041101`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041114`

## pseudocode

```c
__int64 __fastcall SetPartitionType(struct IVdsService *a1, int a2, __int64 a3, int *a4)
{
  int v8; // edi
  int Disk; // ebx
  _BYTE *v10; // rsi
  __int64 v11; // xmm0_8
  struct IVdsAdvancedDisk2 *v13; // [rsp+30h] [rbp-B1h] BYREF
  struct IVdsAdvancedDisk *v14; // [rsp+38h] [rbp-A9h] BYREF
  _BYTE v15[20]; // [rsp+40h] [rbp-A1h] BYREF
  struct IVdsDisk *v16; // [rsp+58h] [rbp-89h] BYREF
  _QWORD v17[2]; // [rsp+60h] [rbp-81h] BYREF
  int v18; // [rsp+70h] [rbp-71h] BYREF
  _BYTE v19[64]; // [rsp+74h] [rbp-6Dh] BYREF
  int v20; // [rsp+B4h] [rbp-2Dh]
  LPVOID pv; // [rsp+C8h] [rbp-19h]
  LPVOID v22; // [rsp+D0h] [rbp-11h]
  LPVOID v23; // [rsp+D8h] [rbp-9h]
  LPVOID v24; // [rsp+E0h] [rbp-1h]
  LPVOID v25; // [rsp+E8h] [rbp+7h]

  v16 = 0;
  v14 = 0;
  v13 = 0;
  v18 = 0;
  memset_0(v19, 0, 0x7Cu);
  if ( !a1 )
    return 2147942487LL;
  if ( a2 < 0 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  v8 = *a4;
  if ( (unsigned int)(*a4 - 1) > 1 )
    return 2147942487LL;
  Disk = GetDisk(a1, a2, &v16, &v14, &v13);
  if ( Disk >= 0 )
  {
    if ( v16 && v14 && v13 )
    {
      Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, int *))v16->lpVtbl->GetProperties)(v16, &v18);
      if ( Disk >= 0 )
      {
        memset(v15, 0, sizeof(v15));
        if ( v8 == 1 )
        {
          if ( v20 == 1 )
          {
            LibLog(
              &g_VdsLibLog,
              0x4000000,
              L"SetPartitionType: The request to set type id and partition specified are both MBR format.");
            v10 = a4 + 1;
            *(_DWORD *)v15 = 1;
            v15[4] = *v10;
LABEL_17:
            Disk = ((__int64 (__fastcall *)(struct IVdsAdvancedDisk2 *, __int64, __int64, _BYTE *))v13->lpVtbl->ChangePartitionType)(
                     v13,
                     a3,
                     1,
                     v15);
            if ( Disk >= 0 && v8 == 2 && !memcmp_0(v10, &PARTITION_MSFT_RECOVERY_GUID, 0x10u) )
            {
              LibLog(
                &g_VdsLibLog,
                0x4000000,
                L"SetPartitionType: This is a recovery partition; setting specific attributes.");
              v17[0] = 2;
              v17[1] = 0x8000000000000001uLL;
              Disk = ((__int64 (__fastcall *)(struct IVdsAdvancedDisk *, __int64, _QWORD *))v14->lpVtbl->ChangeAttributes)(
                       v14,
                       a3,
                       v17);
            }
            goto LABEL_23;
          }
        }
        else if ( v8 == 2 && v20 == 2 )
        {
          LibLog(
            &g_VdsLibLog,
            0x4000000,
            L"SetPartitionType: The request to set type id and partition specified are both GPT format.");
          v11 = *(_QWORD *)((char *)a4 + 5);
          v10 = a4 + 1;
          *(_DWORD *)v15 = 2;
          *(_QWORD *)&v15[5] = v11;
          v15[4] = *v10;
          *(_DWORD *)&v15[13] = *(_DWORD *)(v10 + 9);
          *(_WORD *)&v15[17] = *(_WORD *)(v10 + 13);
          v15[19] = v10[15];
          goto LABEL_17;
        }
        LibLog(
          &g_VdsLibLog,
          0x2000000,
          L"SetPartitionType: Either the partition style for the request [%s] is either unknown, or does not match the sty"
           "le of the specified partition [%s].");
        Disk = -2147211931;
        LibLog(&g_VdsLibLog, 0x2000000, L"SetPartitionType: ChangePartitionType failed, hr = 0x%x.", 2147755365LL);
      }
    }
    else
    {
      Disk = -2147467259;
    }
  }
LABEL_23:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v22 )
  {
    CoTaskMemFree(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    CoTaskMemFree(v23);
    v23 = 0;
  }
  if ( v24 )
  {
    CoTaskMemFree(v24);
    v24 = 0;
  }
  if ( v25 )
  {
    CoTaskMemFree(v25);
    v25 = 0;
  }
  if ( v13 )
  {
    ((void (__fastcall *)(struct IVdsAdvancedDisk2 *))v13->lpVtbl->Release)(v13);
    v13 = 0;
  }
  if ( v14 )
  {
    ((void (__fastcall *)(struct IVdsAdvancedDisk *))v14->lpVtbl->Release)(v14);
    v14 = 0;
  }
  if ( v16 )
    ((void (__fastcall *)(struct IVdsDisk *))v16->lpVtbl->Release)(v16);
  return (unsigned int)Disk;
}

```

## disassembly

```asm
0x180040e44  push    rbp
0x180040e46  push    rbx
0x180040e47  push    rsi
0x180040e48  push    rdi
0x180040e49  push    r12
0x180040e4b  push    r14
0x180040e4d  push    r15
0x180040e4f  lea     rbp, [rsp-1Fh]
0x180040e54  sub     rsp, 100h
0x180040e5b  mov     rax, cs:__security_cookie
0x180040e62  xor     rax, rsp
0x180040e65  mov     [rbp+4Fh+var_40], rax
0x180040e69  xor     r12d, r12d
0x180040e6c  mov     r15, r8
0x180040e6f  mov     ebx, edx
0x180040e71  mov     [rsp+130h+var_D8], r12
0x180040e76  mov     r14, rcx
0x180040e79  mov     [rsp+130h+var_F8], r12
0x180040e7e  xor     edx, edx; Val
0x180040e80  mov     [rsp+130h+var_100], r12
0x180040e85  lea     r8d, [r12+7Ch]; Size
0x180040e8a  mov     [rbp+4Fh+var_C0], r12d
0x180040e8e  lea     rcx, [rbp+4Fh+var_BC]; void *
0x180040e92  mov     rsi, r9
0x180040e95  call    memset_0
0x180040e9a  test    r14, r14
0x180040e9d  jz      loc_18004116E
0x180040ea3  test    ebx, ebx
0x180040ea5  js      loc_18004116E
0x180040eab  test    r15, r15
0x180040eae  jz      loc_18004116E
0x180040eb4  mov     edi, [rsi]
0x180040eb6  lea     eax, [rdi-1]
0x180040eb9  cmp     eax, 1
0x180040ebc  ja      loc_18004116E
0x180040ec2  lea     rax, [rsp+130h+var_100]
0x180040ec7  mov     edx, ebx; int
0x180040ec9  lea     r9, [rsp+130h+var_F8]; struct IVdsAdvancedDisk **
0x180040ece  mov     [rsp+130h+var_110], rax; struct IVdsAdvancedDisk2 **
0x180040ed3  lea     r8, [rsp+130h+var_D8]; struct IVdsDisk **
0x180040ed8  mov     rcx, r14; struct IVdsService *
0x180040edb  call    ?GetDisk@@YAJPEAUIVdsService@@HPEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@PEAPEAUIVdsAdvancedDisk2@@@Z; GetDisk(IVdsService *,int,IVdsDisk * *,IVdsAdvancedDisk * *,IVdsAdvancedDisk2 * *)
0x180040ee0  mov     ebx, eax
0x180040ee2  test    eax, eax
0x180040ee4  js      loc_1800410BF
0x180040eea  mov     rcx, [rsp+130h+var_D8]
0x180040eef  test    rcx, rcx
0x180040ef2  jz      loc_1800410BA
0x180040ef8  cmp     [rsp+130h+var_F8], r12
0x180040efd  jz      loc_1800410BA
0x180040f03  cmp     [rsp+130h+var_100], r12
0x180040f08  jz      loc_1800410BA
0x180040f0e  mov     rax, [rcx]
0x180040f11  lea     rdx, [rbp+4Fh+var_C0]
0x180040f15  mov     rax, [rax+18h]
0x180040f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f1e  mov     ebx, eax
0x180040f20  test    eax, eax
0x180040f22  js      loc_1800410BF
0x180040f28  xor     eax, eax
0x180040f2a  lea     r14d, [r12+2]
0x180040f2f  mov     [rsp+130h+var_E0], eax
0x180040f33  xorps   xmm0, xmm0
0x180040f36  movups  [rsp+130h+var_F0], xmm0
0x180040f3b  cmp     edi, 1
0x180040f3e  jnz     short loc_180040F79
0x180040f40  cmp     [rbp+4Fh+var_7C], edi
0x180040f43  jnz     short loc_180040F6D
0x180040f45  lea     r8, aSetpartitionty_3; "SetPartitionType: The request to set ty"...
0x180040f4c  mov     edx, 4000000h
0x180040f51  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x180040f58  call    LibLog
0x180040f5d  add     rsi, 4
0x180040f61  mov     dword ptr [rsp+130h+var_F0], edi
0x180040f65  mov     al, [rsi]
0x180040f67  mov     byte ptr [rsp+130h+var_F0+4], al
0x180040f6b  jmp     short loc_180040FD5
0x180040f6d  lea     r9, aMbr; "MBR"
0x180040f74  jmp     loc_18004107C
0x180040f79  cmp     edi, r14d
0x180040f7c  jnz     loc_180041075
0x180040f82  cmp     [rbp+4Fh+var_7C], r14d
0x180040f86  jnz     loc_18004106C
0x180040f8c  lea     r8, aSetpartitionty_2; "SetPartitionType: The request to set ty"...
0x180040f93  mov     edx, 4000000h
0x180040f98  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x180040f9f  call    LibLog
0x180040fa4  movsd   xmm0, qword ptr [rsi+5]
0x180040fa9  add     rsi, 4
0x180040fad  mov     dword ptr [rsp+130h+var_F0], r14d
0x180040fb2  movsd   qword ptr [rsp+130h+var_F0+5], xmm0
0x180040fb8  mov     al, [rsi]
0x180040fba  mov     byte ptr [rsp+130h+var_F0+4], al
0x180040fbe  mov     eax, [rsi+9]
0x180040fc1  mov     dword ptr [rsp+130h+var_F0+0Dh], eax
0x180040fc5  movzx   eax, word ptr [rsi+0Dh]
0x180040fc9  mov     word ptr [rsp+130h+var_E0+1], ax
0x180040fce  mov     al, [rsi+0Fh]
0x180040fd1  mov     byte ptr [rsp+130h+var_E0+3], al
0x180040fd5  mov     rcx, [rsp+130h+var_100]
0x180040fda  lea     r9, [rsp+130h+var_F0]
0x180040fdf  mov     r8d, 1
0x180040fe5  mov     rdx, r15
0x180040fe8  mov     rax, [rcx]
0x180040feb  mov     rax, [rax+18h]
0x180040fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ff4  mov     ebx, eax
0x180040ff6  test    eax, eax
0x180040ff8  js      loc_1800410BF
0x180040ffe  cmp     edi, r14d
0x180041001  jnz     loc_1800410BF
0x180041007  mov     r8d, 10h; Size
0x18004100d  lea     rdx, PARTITION_MSFT_RECOVERY_GUID; Buf2
0x180041014  mov     rcx, rsi; Buf1
0x180041017  call    memcmp_0
0x18004101c  test    eax, eax
0x18004101e  jnz     loc_1800410BF
0x180041024  lea     r8, aSetpartitionty_0; "SetPartitionType: This is a recovery pa"...
0x18004102b  mov     edx, 4000000h
0x180041030  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x180041037  call    LibLog
0x18004103c  mov     rcx, [rsp+130h+var_F8]
0x180041041  lea     r8, [rsp+130h+var_D0]
0x180041046  mov     rax, 8000000000000001h
0x180041050  mov     [rsp+130h+var_D0], r14
0x180041055  mov     [rbp+4Fh+var_C8], rax
0x180041059  mov     rdx, r15
0x18004105c  mov     rax, [rcx]
0x18004105f  mov     rax, [rax+38h]
0x180041063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041068  mov     ebx, eax
0x18004106a  jmp     short loc_1800410BF
0x18004106c  lea     r9, aGpt; "GPT"
0x180041073  jmp     short loc_18004107C
0x180041075  lea     r9, aUnk; "UNK"
0x18004107c  mov     edi, 2000000h
0x180041081  mov     [rsp+130h+var_110], r9
0x180041086  mov     edx, edi
0x180041088  lea     r8, aSetpartitionty; "SetPartitionType: Either the partition "...
0x18004108f  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x180041096  call    LibLog
0x18004109b  mov     ebx, 80042565h
0x1800410a0  lea     r8, aSetpartitionty_1; "SetPartitionType: ChangePartitionType f"...
0x1800410a7  mov     r9d, ebx
0x1800410aa  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x1800410b1  mov     edx, edi
0x1800410b3  call    LibLog
0x1800410b8  jmp     short loc_1800410BF
0x1800410ba  mov     ebx, 80004005h
0x1800410bf  mov     rcx, [rbp+4Fh+pv]; pv
0x1800410c3  test    rcx, rcx
0x1800410c6  jz      short loc_1800410D2
0x1800410c8  call    cs:__imp_CoTaskMemFree
0x1800410ce  mov     [rbp+4Fh+pv], r12
0x1800410d2  mov     rcx, [rbp+4Fh+var_60]; pv
0x1800410d6  test    rcx, rcx
0x1800410d9  jz      short loc_1800410E5
0x1800410db  call    cs:__imp_CoTaskMemFree
0x1800410e1  mov     [rbp+4Fh+var_60], r12
0x1800410e5  mov     rcx, [rbp+4Fh+var_58]; pv
0x1800410e9  test    rcx, rcx
0x1800410ec  jz      short loc_1800410F8
0x1800410ee  call    cs:__imp_CoTaskMemFree
0x1800410f4  mov     [rbp+4Fh+var_58], r12
0x1800410f8  mov     rcx, [rbp+4Fh+var_50]; pv
0x1800410fc  test    rcx, rcx
0x1800410ff  jz      short loc_18004110B
0x180041101  call    cs:__imp_CoTaskMemFree
0x180041107  mov     [rbp+4Fh+var_50], r12
0x18004110b  mov     rcx, [rbp+4Fh+var_48]; pv
0x18004110f  test    rcx, rcx
0x180041112  jz      short loc_18004111E
0x180041114  call    cs:__imp_CoTaskMemFree
0x18004111a  mov     [rbp+4Fh+var_48], r12
0x18004111e  mov     rcx, [rsp+130h+var_100]
0x180041123  test    rcx, rcx
0x180041126  jz      short loc_180041139
0x180041128  mov     rax, [rcx]
0x18004112b  mov     rax, [rax+10h]
0x18004112f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041134  mov     [rsp+130h+var_100], r12
0x180041139  mov     rcx, [rsp+130h+var_F8]
0x18004113e  test    rcx, rcx
0x180041141  jz      short loc_180041154
0x180041143  mov     rax, [rcx]
0x180041146  mov     rax, [rax+10h]
0x18004114a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004114f  mov     [rsp+130h+var_F8], r12
0x180041154  mov     rcx, [rsp+130h+var_D8]
0x180041159  test    rcx, rcx
0x18004115c  jz      short loc_18004116A
0x18004115e  mov     rax, [rcx]
0x180041161  mov     rax, [rax+10h]
0x180041165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004116a  mov     eax, ebx
0x18004116c  jmp     short loc_180041173
0x18004116e  mov     eax, 80070057h
0x180041173  mov     rcx, [rbp+4Fh+var_40]
0x180041177  xor     rcx, rsp; StackCookie
0x18004117a  call    __security_check_cookie
0x18004117f  add     rsp, 100h
0x180041186  pop     r15
0x180041188  pop     r14
0x18004118a  pop     r12
0x18004118c  pop     rdi
0x18004118d  pop     rsi
0x18004118e  pop     rbx
0x18004118f  pop     rbp
0x180041190  retn
```
