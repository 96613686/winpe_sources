# CWinInetHelperClass::GetRepairInfo(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x180007800`
- end: `0x180007c59`
- name: `?GetRepairInfo@CWinInetHelperClass@@UEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `1113`
- prototype: `__int64 __fastcall(CWinInetHelperClass *__hidden this, enum tagPROBLEM_TYPE, unsigned int *, struct tagRepairInfo **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180007800`
- `0x18000c998`
- `0x180010324`
- `0x1800120e8`
- `0x180012510`
- `0x180012d56`
- `0x180012d6e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000799a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007ac8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000799a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007ac8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007bae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007bae`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::GetRepairInfo(
        CWinInetHelperClass *this,
        enum tagPROBLEM_TYPE a2,
        unsigned int *a3,
        struct tagRepairInfo **a4)
{
  int v7; // eax
  __int128 v8; // xmm0
  __int64 v9; // rcx
  int v10; // ebx
  struct tagRepairInfo *v11; // rax
  struct tagRepairInfo *v12; // rsi
  int v13; // ebp
  unsigned int v14; // ebx
  _OWORD *i; // rcx
  __int64 v16; // r12
  unsigned int v17; // r12d
  __int128 v18; // kr00_16
  __int128 v19; // kr10_16
  __int128 v20; // kr20_16
  __int64 v21; // rbp
  unsigned __int64 v22; // rsi
  unsigned __int16 *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  _OWORD v27[5]; // [rsp+20h] [rbp-58h] BYREF

  if ( !a3 || !a4 )
    return (unsigned int)-2147024809;
  *a3 = 0;
  if ( *((_DWORD *)this + 287) == 3 || *((_DWORD *)this + 1105) )
    return 0;
  if ( !*((_DWORD *)this + 1274) || (v7 = *((_DWORD *)this + 754), v7 == 7) )
  {
    v8 = *(_OWORD *)&ID_WINETHC_REPAIR_INVALID_URL;
    goto LABEL_39;
  }
  if ( !*((_DWORD *)this + 1275) )
  {
    if ( v7 == 8 )
    {
      v8 = ID_WINETHC_REPAIR_PROXYSENTBADGATEWAY;
      goto LABEL_39;
    }
    if ( *((_DWORD *)this + 1238) )
    {
      v8 = ID_WINETHC_REPAIR_AUTODETECTTIMEOUT;
      goto LABEL_39;
    }
    if ( v7 == 6 )
    {
      v8 = ID_WINETHC_REPAIR_FORBIDDEN;
      goto LABEL_39;
    }
    v9 = *((_QWORD *)this + 639);
    if ( v9 && *(_DWORD *)(v9 + 4) != 1 )
    {
      if ( !*(_DWORD *)(v9 + 4) )
        return 0;
      v8 = ID_WINETHC_REPAIR_DOMAINPROXY;
      goto LABEL_39;
    }
    if ( !*((_DWORD *)this + 1214)
      && (!*((_QWORD *)this + 609) || !*((_DWORD *)this + 788))
      && (*((_QWORD *)this + 613) || *((_DWORD *)this + 1240))
      && !*((_QWORD *)this + 608)
      || *((_DWORD *)this + 1277) == 1 )
    {
      v8 = ID_WINETHC_REPAIR_AUTOCONFIGPROXY;
      goto LABEL_39;
    }
    if ( (*((_QWORD *)this + 609) || *((_QWORD *)this + 608) && *((_DWORD *)this + 790))
      && !*((_DWORD *)this + 788)
      && *((_DWORD *)this + 1222) )
    {
      v8 = ID_WINETHC_REPAIR_MANUALPROXY;
      goto LABEL_39;
    }
    if ( (v7 == 2 || *((_DWORD *)this + 1212)) && *((_DWORD *)this + 1239) )
    {
      v8 = ID_WINETHC_REPAIR_HOTSPOT;
      goto LABEL_39;
    }
    return 0;
  }
  v8 = ID_WINETHC_REPAIR_PROXYAUTODETECTIONFAILURE;
LABEL_39:
  v27[0] = v8;
  v11 = (struct tagRepairInfo *)CoTaskMemAlloc(0x70u);
  v12 = v11;
  if ( v11 )
  {
    memset_0(v11, 0, sizeof(struct tagRepairInfo));
    v13 = 0;
    while ( 1 )
    {
      v14 = 0;
      for ( i = &v27[v13]; ; i = &v27[v13] )
      {
        v16 = 120LL * v14;
        if ( !memcmp_0(i, (char *)&CWinInetHelperClass::m_repairInfos + v16 + 8, 0x10u) )
          break;
        if ( ++v14 >= 9 )
          goto LABEL_65;
      }
      if ( !(const struct tagRepairInfoMap near *const *)((char *)&CWinInetHelperClass::m_repairInfos + v16) )
        break;
      v10 = PopulateRepairInfo(
              (const struct tagRepairInfoMap *)((char *)&CWinInetHelperClass::m_repairInfos + v16),
              &v12[v13]);
      if ( v10 < 0 )
        goto LABEL_66;
      if ( ++v13 )
      {
        *a3 = 1;
        v10 = 0;
        *a4 = v12;
        if ( !v12 )
          return (unsigned int)v10;
        v17 = 0;
        if ( !*a3 )
          return (unsigned int)v10;
        v18 = ID_WINETHC_REPAIR_HOTSPOT;
        v19 = ID_WINETHC_REPAIR_FORBIDDEN;
        v20 = *(_OWORD *)&ID_WINETHC_REPAIR_INVALID_URL;
        while ( 2 )
        {
          v21 = (__int64)*a4;
          v22 = 112LL * v17;
          if ( *(_OWORD *)&(*a4)[v22 / 0x70].guid == v19 )
          {
            v23 = (unsigned __int16 *)CoTaskMemAlloc(0x74u);
            *(_QWORD *)(v22 + v21 + 64) = v23;
            if ( !v23 )
              return (unsigned int)-2147024882;
            StringCchCopyW(v23, 0x3Au, L"mshelp://Windows/?id=fbbb222b-5397-44a0-81a9-8384130cba9c");
            *(_WORD *)(*(_QWORD *)(v22 + v21 + 64) + 114LL) = 0;
            *(_DWORD *)(v22 + v21 + 56) = 3;
LABEL_61:
            v18 = ID_WINETHC_REPAIR_HOTSPOT;
            v19 = ID_WINETHC_REPAIR_FORBIDDEN;
            v20 = *(_OWORD *)&ID_WINETHC_REPAIR_INVALID_URL;
          }
          else
          {
            if ( *(_OWORD *)(v22 + v21) == v18 )
            {
              *(_DWORD *)(v22 + v21 + 56) = 2;
              v10 = AssembleStringsWithAlloc(
                      (unsigned __int16 **)(v22 + v21 + 64),
                      v20,
                      L"open",
                      (unsigned __int16 *)&byte_180017BD0);
              if ( v10 < 0 )
                return (unsigned int)v10;
              v10 = AssembleStringsWithAlloc(
                      (unsigned __int16 **)(v22 + v21 + 72),
                      v24,
                      (unsigned __int16 *)this + 576,
                      (unsigned __int16 *)&byte_180017BD0);
              if ( v10 < 0 )
                return (unsigned int)v10;
              v18 = ID_WINETHC_REPAIR_HOTSPOT;
              v19 = ID_WINETHC_REPAIR_FORBIDDEN;
              v20 = *(_OWORD *)&ID_WINETHC_REPAIR_INVALID_URL;
            }
            if ( *(_OWORD *)(v22 + v21) == v20 )
            {
              CoTaskMemFree(*(LPVOID *)(v22 + v21 + 24));
              *(_QWORD *)(v22 + v21 + 24) = 0;
              v10 = AssembleStringsWithAlloc(
                      (unsigned __int16 **)(v22 + v21 + 24),
                      v25,
                      (unsigned __int16 *)0x2C5,
                      (unsigned __int16 *)this + 875);
              if ( v10 < 0 )
                return (unsigned int)v10;
              goto LABEL_61;
            }
          }
          if ( ++v17 >= *a3 )
            return (unsigned int)v10;
          continue;
        }
      }
    }
LABEL_65:
    v10 = -2147023728;
LABEL_66:
    FreeRepairInfos(v12, 1u, 1);
  }
  else
  {
    v10 = -2147024882;
  }
  *a3 = 0;
  *a4 = 0;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180007800  push    rbx
0x180007802  push    rbp
0x180007803  push    rsi
0x180007804  push    rdi
0x180007805  push    r12
0x180007807  push    r13
0x180007809  push    r14
0x18000780b  push    r15
0x18000780d  sub     rsp, 38h
0x180007811  xor     r15d, r15d
0x180007814  mov     r13, r9
0x180007817  mov     r14, r8
0x18000781a  mov     rdi, rcx
0x18000781d  test    r8, r8
0x180007820  jz      loc_180007C40
0x180007826  test    r9, r9
0x180007829  jz      loc_180007C40
0x18000782f  mov     [r8], r15d
0x180007832  cmp     dword ptr [rcx+47Ch], 3
0x180007839  jz      loc_180007C3C
0x18000783f  cmp     [rcx+1144h], r15d
0x180007846  jnz     loc_180007C3C
0x18000784c  cmp     [rcx+13E8h], r15d
0x180007853  jz      loc_180007986
0x180007859  mov     eax, [rcx+0BC8h]
0x18000785f  cmp     eax, 7
0x180007862  jz      loc_180007986
0x180007868  cmp     [rcx+13ECh], r15d
0x18000786f  jz      short loc_18000787D
0x180007871  movups  xmm0, cs:ID_WINETHC_REPAIR_PROXYAUTODETECTIONFAILURE
0x180007878  jmp     loc_18000798D
0x18000787d  cmp     eax, 8
0x180007880  jnz     short loc_18000788E
0x180007882  movups  xmm0, cs:ID_WINETHC_REPAIR_PROXYSENTBADGATEWAY
0x180007889  jmp     loc_18000798D
0x18000788e  cmp     [rcx+1358h], r15d
0x180007895  jz      short loc_1800078A3
0x180007897  movups  xmm0, cs:ID_WINETHC_REPAIR_AUTODETECTTIMEOUT
0x18000789e  jmp     loc_18000798D
0x1800078a3  cmp     eax, 6
0x1800078a6  jnz     short loc_1800078B4
0x1800078a8  movups  xmm0, cs:ID_WINETHC_REPAIR_FORBIDDEN
0x1800078af  jmp     loc_18000798D
0x1800078b4  mov     rcx, [rcx+13F8h]
0x1800078bb  test    rcx, rcx
0x1800078be  jz      short loc_1800078E0
0x1800078c0  cmp     dword ptr [rcx+4], 1
0x1800078c4  jz      short loc_1800078E0
0x1800078c6  cmp     [rcx+4], r15d
0x1800078ca  jnz     short loc_1800078D4
0x1800078cc  mov     ebx, r15d
0x1800078cf  jmp     loc_180007C45
0x1800078d4  movups  xmm0, cs:ID_WINETHC_REPAIR_DOMAINPROXY
0x1800078db  jmp     loc_18000798D
0x1800078e0  cmp     [rdi+12F8h], r15d
0x1800078e7  jnz     short loc_180007916
0x1800078e9  cmp     [rdi+1308h], r15
0x1800078f0  jz      short loc_1800078FB
0x1800078f2  cmp     [rdi+0C50h], r15d
0x1800078f9  jnz     short loc_180007916
0x1800078fb  cmp     [rdi+1328h], r15
0x180007902  jnz     short loc_18000790D
0x180007904  cmp     [rdi+1360h], r15d
0x18000790b  jz      short loc_180007916
0x18000790d  cmp     [rdi+1300h], r15
0x180007914  jz      short loc_18000791F
0x180007916  cmp     dword ptr [rdi+13F4h], 1
0x18000791d  jnz     short loc_180007928
0x18000791f  movups  xmm0, cs:ID_WINETHC_REPAIR_AUTOCONFIGPROXY
0x180007926  jmp     short loc_18000798D
0x180007928  cmp     [rdi+1308h], r15
0x18000792f  jnz     short loc_180007943
0x180007931  cmp     [rdi+1300h], r15
0x180007938  jz      short loc_18000795E
0x18000793a  cmp     [rdi+0C58h], r15d
0x180007941  jz      short loc_18000795E
0x180007943  cmp     [rdi+0C50h], r15d
0x18000794a  jnz     short loc_18000795E
0x18000794c  cmp     [rdi+1318h], r15d
0x180007953  jz      short loc_18000795E
0x180007955  movups  xmm0, cs:ID_WINETHC_REPAIR_MANUALPROXY
0x18000795c  jmp     short loc_18000798D
0x18000795e  cmp     eax, 2
0x180007961  jz      short loc_180007970
0x180007963  cmp     [rdi+12F0h], r15d
0x18000796a  jz      loc_180007C3C
0x180007970  cmp     [rdi+135Ch], r15d
0x180007977  jz      loc_180007C3C
0x18000797d  movups  xmm0, cs:ID_WINETHC_REPAIR_HOTSPOT
0x180007984  jmp     short loc_18000798D
0x180007986  movups  xmm0, cs:ID_WINETHC_REPAIR_INVALID_URL
0x18000798d  mov     ebx, 70h ; 'p'
0x180007992  mov     ecx, ebx; cb
0x180007994  movdqu  [rsp+78h+var_58], xmm0
0x18000799a  call    cs:__imp_CoTaskMemAlloc
0x1800079a1  nop     dword ptr [rax+rax+00h]
0x1800079a6  mov     rsi, rax
0x1800079a9  test    rax, rax
0x1800079ac  jnz     short loc_1800079B8
0x1800079ae  mov     ebx, 8007000Eh
0x1800079b3  jmp     loc_180007C33
0x1800079b8  mov     r8, rbx; Size
0x1800079bb  xor     edx, edx; Val
0x1800079bd  mov     rcx, rsi; void *
0x1800079c0  call    memset_0
0x1800079c5  lea     rdx, ?m_repairInfos@CWinInetHelperClass@@0QBUtagRepairInfoMap@@B; tagRepairInfoMap const near * const CWinInetHelperClass::m_repairInfos
0x1800079cc  mov     ebp, r15d
0x1800079cf  mov     eax, ebp
0x1800079d1  lea     rcx, [rsp+78h+var_58]
0x1800079d6  shl     rax, 4
0x1800079da  mov     ebx, r15d
0x1800079dd  add     rcx, rax; Buf1
0x1800079e0  mov     r15d, ebp
0x1800079e3  mov     [rsp+78h+arg_10], rcx
0x1800079eb  mov     eax, ebx
0x1800079ed  add     rdx, 8
0x1800079f1  imul    r12, rax, 78h ; 'x'
0x1800079f5  mov     r8d, 10h; Size
0x1800079fb  add     rdx, r12; Buf2
0x1800079fe  call    memcmp_0
0x180007a03  test    eax, eax
0x180007a05  jz      short loc_180007A23
0x180007a07  inc     ebx
0x180007a09  cmp     ebx, 9
0x180007a0c  jnb     loc_180007C19
0x180007a12  mov     rcx, [rsp+78h+arg_10]
0x180007a1a  lea     rdx, ?m_repairInfos@CWinInetHelperClass@@0QBUtagRepairInfoMap@@B; tagRepairInfoMap const near * const CWinInetHelperClass::m_repairInfos
0x180007a21  jmp     short loc_1800079EB
0x180007a23  lea     rcx, ?m_repairInfos@CWinInetHelperClass@@0QBUtagRepairInfoMap@@B; tagRepairInfoMap const near * const CWinInetHelperClass::m_repairInfos
0x180007a2a  add     rcx, r12; struct tagRepairInfoMap *
0x180007a2d  jz      loc_180007C19
0x180007a33  imul    rdx, r15, 70h ; 'p'
0x180007a37  add     rdx, rsi; struct tagRepairInfo *
0x180007a3a  call    ?PopulateRepairInfo@@YAJPEBUtagRepairInfoMap@@PEAUtagRepairInfo@@@Z; PopulateRepairInfo(tagRepairInfoMap const *,tagRepairInfo *)
0x180007a3f  xor     r15d, r15d
0x180007a42  mov     ebx, eax
0x180007a44  test    eax, eax
0x180007a46  js      loc_180007C21
0x180007a4c  inc     ebp
0x180007a4e  lea     rdx, ?m_repairInfos@CWinInetHelperClass@@0QBUtagRepairInfoMap@@B; tagRepairInfoMap const near * const CWinInetHelperClass::m_repairInfos
0x180007a55  cmp     ebp, 1
0x180007a58  jb      loc_1800079CF
0x180007a5e  mov     dword ptr [r14], 1
0x180007a65  mov     ebx, r15d
0x180007a68  mov     [r13+0], rsi
0x180007a6c  test    rsi, rsi
0x180007a6f  jz      loc_180007C45
0x180007a75  mov     r12d, r15d
0x180007a78  cmp     [r14], r15d
0x180007a7b  jbe     loc_180007C45
0x180007a81  mov     rcx, qword ptr cs:ID_WINETHC_REPAIR_INVALID_URL+8
0x180007a88  mov     rdx, qword ptr cs:ID_WINETHC_REPAIR_INVALID_URL; unsigned int
0x180007a8f  mov     r8, qword ptr cs:ID_WINETHC_REPAIR_FORBIDDEN+8
0x180007a96  mov     r11, qword ptr cs:ID_WINETHC_REPAIR_FORBIDDEN
0x180007a9d  mov     r9, qword ptr cs:ID_WINETHC_REPAIR_HOTSPOT+8
0x180007aa4  mov     r10, qword ptr cs:ID_WINETHC_REPAIR_HOTSPOT
0x180007aab  mov     rbp, [r13+0]
0x180007aaf  mov     eax, r12d
0x180007ab2  imul    rsi, rax, 70h ; 'p'
0x180007ab6  cmp     [rsi+rbp], r11
0x180007aba  jnz     short loc_180007B0D
0x180007abc  cmp     [rsi+rbp+8], r8
0x180007ac1  jnz     short loc_180007B0D
0x180007ac3  mov     ecx, 74h ; 't'; cb
0x180007ac8  call    cs:__imp_CoTaskMemAlloc
0x180007acf  nop     dword ptr [rax+rax+00h]
0x180007ad4  mov     [rsi+rbp+40h], rax
0x180007ad9  test    rax, rax
0x180007adc  jz      loc_180007C12
0x180007ae2  lea     r8, aMshelpWindowsI; "mshelp://Windows/?id=fbbb222b-5397-44a0"...
0x180007ae9  mov     edx, 3Ah ; ':'; unsigned __int64
0x180007aee  mov     rcx, rax; unsigned __int16 *
0x180007af1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007af6  mov     r11, [rsi+rbp+40h]
0x180007afb  mov     [r11+72h], r15w
0x180007b00  mov     dword ptr [rsi+rbp+38h], 3
0x180007b08  jmp     loc_180007BDA
0x180007b0d  cmp     [rsi+rbp], r10
0x180007b11  jnz     loc_180007B99
0x180007b17  cmp     [rsi+rbp+8], r9
0x180007b1c  jnz     short loc_180007B99
0x180007b1e  lea     r15, [rsi+rbp]
0x180007b22  mov     dword ptr [rsi+rbp+38h], 2
0x180007b2a  lea     rcx, [r15+40h]; unsigned __int16 **
0x180007b2e  lea     r9, byte_180017BD0; unsigned __int16 *
0x180007b35  lea     r8, aOpen; "open"
0x180007b3c  call    ?AssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1@Z; AssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *)
0x180007b41  mov     ebx, eax
0x180007b43  test    eax, eax
0x180007b45  js      loc_180007C45
0x180007b4b  lea     r8, [rdi+480h]; unsigned __int16 *
0x180007b52  lea     rcx, [r15+48h]; unsigned __int16 **
0x180007b56  lea     r9, byte_180017BD0; unsigned __int16 *
0x180007b5d  call    ?AssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1@Z; AssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *)
0x180007b62  xor     r15d, r15d
0x180007b65  mov     ebx, eax
0x180007b67  test    eax, eax
0x180007b69  js      loc_180007C45
0x180007b6f  mov     rcx, qword ptr cs:ID_WINETHC_REPAIR_INVALID_URL+8
0x180007b76  mov     rdx, qword ptr cs:ID_WINETHC_REPAIR_INVALID_URL
0x180007b7d  mov     r8, qword ptr cs:ID_WINETHC_REPAIR_FORBIDDEN+8
0x180007b84  mov     r11, qword ptr cs:ID_WINETHC_REPAIR_FORBIDDEN
0x180007b8b  mov     r9, qword ptr cs:ID_WINETHC_REPAIR_HOTSPOT+8
0x180007b92  mov     r10, qword ptr cs:ID_WINETHC_REPAIR_HOTSPOT
0x180007b99  cmp     [rsi+rbp], rdx
0x180007b9d  jnz     short loc_180007C04
0x180007b9f  cmp     [rsi+rbp+8], rcx
0x180007ba4  jnz     short loc_180007C04
0x180007ba6  lea     rbx, [rsi+rbp]
0x180007baa  mov     rcx, [rbx+18h]; pv
0x180007bae  call    cs:__imp_CoTaskMemFree
0x180007bb5  nop     dword ptr [rax+rax+00h]
0x180007bba  lea     r9, [rdi+6D6h]; unsigned __int16 *
0x180007bc1  mov     [rbx+18h], r15
0x180007bc5  mov     r8d, 2C5h; unsigned __int16 *
0x180007bcb  lea     rcx, [rbx+18h]; unsigned __int16 **
0x180007bcf  call    ?AssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1@Z; AssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *)
0x180007bd4  mov     ebx, eax
0x180007bd6  test    eax, eax
0x180007bd8  js      short loc_180007C45
0x180007bda  mov     r10, qword ptr cs:ID_WINETHC_REPAIR_HOTSPOT
0x180007be1  mov     r9, qword ptr cs:ID_WINETHC_REPAIR_HOTSPOT+8
0x180007be8  mov     r11, qword ptr cs:ID_WINETHC_REPAIR_FORBIDDEN
0x180007bef  mov     r8, qword ptr cs:ID_WINETHC_REPAIR_FORBIDDEN+8
0x180007bf6  mov     rdx, qword ptr cs:ID_WINETHC_REPAIR_INVALID_URL
0x180007bfd  mov     rcx, qword ptr cs:ID_WINETHC_REPAIR_INVALID_URL+8
0x180007c04  inc     r12d
0x180007c07  cmp     r12d, [r14]
0x180007c0a  jb      loc_180007AAB
0x180007c10  jmp     short loc_180007C45
0x180007c12  mov     ebx, 8007000Eh
0x180007c17  jmp     short loc_180007C45
0x180007c19  mov     ebx, 80070490h
0x180007c1e  xor     r15d, r15d
0x180007c21  mov     eax, 1
0x180007c26  mov     rcx, rsi; pv
0x180007c29  mov     r8d, eax; int
0x180007c2c  mov     edx, eax; unsigned int
0x180007c2e  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x180007c33  mov     [r14], r15d
0x180007c36  mov     [r13+0], r15
0x180007c3a  jmp     short loc_180007C45
0x180007c3c  xor     eax, eax
0x180007c3e  jmp     short loc_180007C47
0x180007c40  mov     ebx, 80070057h
0x180007c45  mov     eax, ebx
0x180007c47  add     rsp, 38h
0x180007c4b  pop     r15
0x180007c4d  pop     r14
0x180007c4f  pop     r13
0x180007c51  pop     r12
0x180007c53  pop     rdi
0x180007c54  pop     rsi
0x180007c55  pop     rbp
0x180007c56  pop     rbx
0x180007c57  retn
```
