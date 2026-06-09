# HostProxyResultNode::Initialize(ushort const *,ProxyResolveScheme,ushort const *,ulong,void *,_PROXY_CONFIG_INFO const *)

- ea: `0x18000a954`
- end: `0x18000aefa`
- name: `?Initialize@HostProxyResultNode@@AEAAJPEBGW4ProxyResolveScheme@@0KPEAXPEBU_PROXY_CONFIG_INFO@@@Z`
- size: `1446`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a0c4`

## callees

- `0x18000a954`
- `0x18000af00`
- `0x18000afbc`
- `0x18000bfd0`
- `0x18001b480`
- `0x18001c504`
- `0x18001cf34`
- `0x18007bca4`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800bfe90`
- `0x1800d5448`
- `0x1800d84cc`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000adc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000adcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000adc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000adcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac29`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000adf1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000adf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aa1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aa1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac5f`

## pseudocode

```c
__int64 __fastcall HostProxyResultNode::Initialize(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned __int16 *a4,
        int a5,
        void *a6,
        __int64 a7)
{
  __int64 *v8; // r12
  struct IProxyDetectionHandle *v10; // rsi
  struct IProxyDetectionHandle *v11; // rdi
  __int64 v12; // r14
  struct IProxyDetectionHandle *v13; // rbx
  struct IProxyDetectionHandle *v14; // rax
  struct IProxyDetectionHandle *v15; // r12
  unsigned int v16; // eax
  __int64 v17; // rdx
  _WORD *v18; // rax
  __int64 v19; // rcx
  struct IProxyDetectionHandle *v20; // rcx
  signed int v21; // r14d
  int v22; // eax
  HANDLE v23; // r14
  struct IProxyDetectionHandle *v24; // rbx
  int v25; // ebx
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  HANDLE v28; // rax
  __int64 v29; // rax
  __int128 v30; // xmm0
  unsigned int v31; // r15d
  signed int LastError; // eax
  HANDLE CurrentProcess; // rbx
  HANDLE v35; // rax
  DWORD dwDesiredAccess[2]; // [rsp+20h] [rbp-C1h]
  struct IProxyDetectionHandle *v37; // [rsp+60h] [rbp-81h] BYREF
  HANDLE hSourceHandle; // [rsp+68h] [rbp-79h] BYREF
  __int64 *v39; // [rsp+70h] [rbp-71h] BYREF
  __int64 v40; // [rsp+78h] [rbp-69h]
  int v41; // [rsp+84h] [rbp-5Dh]
  int v42; // [rsp+88h] [rbp-59h]
  _WORD *v43; // [rsp+90h] [rbp-51h]
  struct _PROXY_CONFIG_INFO *v44; // [rsp+98h] [rbp-49h]
  unsigned __int16 *v45; // [rsp+A0h] [rbp-41h]
  HANDLE hObject; // [rsp+A8h] [rbp-39h] BYREF
  __int128 v47; // [rsp+B0h] [rbp-31h] BYREF
  HANDLE v48[2]; // [rsp+C0h] [rbp-21h]
  __int128 v49; // [rsp+D0h] [rbp-11h]
  __int64 v50; // [rsp+E0h] [rbp-1h]

  v43 = (_WORD *)a2;
  v45 = a4;
  v42 = a3;
  HIDWORD(v37) = 0;
  v8 = qword_1800E7D10;
  v44 = (struct _PROXY_CONFIG_INFO *)a7;
  v10 = 0;
  hSourceHandle = a6;
  v11 = 0;
  v50 = 0;
  v39 = qword_1800E7D10;
  v40 = 0;
  hObject = 0;
  v47 = 0;
  *(_OWORD *)v48 = 0;
  v49 = 0;
  if ( a7 )
  {
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_qSDSqDDqD(
        a7,
        (_DWORD)a6,
        a3,
        a1,
        a2,
        a3,
        (__int64)a4,
        (__int64)a6,
        a5,
        *(_DWORD *)(a7 + 24),
        *(_QWORD *)(a7 + 16),
        *(_DWORD *)(a7 + 36));
    if ( a2 )
    {
      v41 = 0;
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(a2 + 2 * v12) );
      v41 = 0;
      v13 = 0;
      v37 = 0;
      v14 = (struct IProxyDetectionHandle *)CoTaskMemAlloc((unsigned int)(2 * v12 + 2));
      v15 = v14;
      if ( !v14 )
      {
        v21 = -2147024882;
        v41 = 544;
        goto LABEL_19;
      }
      memset_0(v14, 0, (unsigned int)(2 * v12 + 2));
      v13 = v15;
      v37 = v15;
      v16 = v12 + 1;
      v17 = (unsigned int)(v12 + 1);
      if ( (_DWORD)v12 == -1 )
      {
        v21 = -2147024809;
        if ( !v16 )
          goto LABEL_17;
      }
      else if ( v16 <= 0x7FFFFFFFuLL )
      {
        v18 = v43;
        v19 = 2147483646;
        do
        {
          if ( !v19 )
            break;
          if ( !*v18 )
            break;
          *(_WORD *)v15 = *v18++;
          v15 = (struct IProxyDetectionHandle *)((char *)v15 + 2);
          --v19;
          --v17;
        }
        while ( v17 );
        v20 = (struct IProxyDetectionHandle *)((char *)v15 - 2);
        if ( v17 )
          v20 = v15;
        v21 = v17 == 0 ? 0x8007007A : 0;
        *(_WORD *)v20 = 0;
LABEL_17:
        if ( v21 >= 0 )
        {
          v10 = v13;
          v13 = 0;
          v37 = 0;
          goto LABEL_19;
        }
        goto LABEL_65;
      }
      *(_WORD *)v15 = 0;
      v21 = -2147024809;
LABEL_65:
      v41 = 548;
LABEL_19:
      if ( v13 )
        WxCoTaskAllocator::Free((void **)&v37);
      if ( v21 >= 0 )
      {
        v22 = WxCopyProxyConfigInfo(0, v44, (struct _PROXY_CONFIG_INFO *)&v47);
        v21 = v22;
        if ( v22 < 0 )
        {
          HIDWORD(v37) = 537;
        }
        else
        {
          if ( !v45 || (v22 = CWxString::Set((CWxString *)&v39, v45), v21 = v22, v22 >= 0) )
          {
            v23 = hSourceHandle;
            if ( hSourceHandle )
            {
              CurrentProcess = GetCurrentProcess();
              v35 = GetCurrentProcess();
              if ( !DuplicateHandle(v35, v23, CurrentProcess, &hObject, 0, 0, 2u) )
              {
                LastError = GetLastError();
                v21 = LastError;
                if ( LastError > 0 )
                  v21 = (unsigned __int16)LastError | 0x80070000;
                if ( v21 >= 0 )
                  v21 = -2147418113;
                HIDWORD(v37) = 552;
                goto LABEL_43;
              }
              if ( (xmmword_180107A60 & 0x20) != 0 )
                WPP_SF_qq(
                  1029,
                  22,
                  (unsigned int)WPP_ca560ec3f10535b7d2ca7712797057c8_Traceguids,
                  (_DWORD)v23,
                  (__int64)hObject);
            }
            v24 = 0;
            HIDWORD(hSourceHandle) = 0;
            v37 = 0;
            if ( (xmmword_180107A60 & 0x20) != 0 )
              WPP_SF_q(1029, 19, WPP_ca560ec3f10535b7d2ca7712797057c8_Traceguids);
            if ( v48[0] )
            {
              v21 = CProxyDetectionHandle::CreateDuplicateDetectionHandle(v48[0], &v37);
              if ( v21 >= 0 )
              {
                v11 = v37;
              }
              else
              {
                v24 = v37;
                HIDWORD(hSourceHandle) = 489;
              }
            }
            else
            {
              v21 = 0;
            }
            if ( (xmmword_180107A60 & 0x20) != 0 )
              WPP_SF_d(
                1029,
                20,
                WPP_ca560ec3f10535b7d2ca7712797057c8_Traceguids,
                (unsigned int)v21,
                *(_QWORD *)dwDesiredAccess);
            if ( v24 )
              (*(void (__fastcall **)(struct IProxyDetectionHandle *))(*(_QWORD *)v24 + 16LL))(v24);
            if ( v21 < 0 )
            {
              HIDWORD(v37) = 562;
            }
            else
            {
              if ( v11 )
              {
                *(_QWORD *)(a1 + 128) = v11;
                v11 = 0;
                AutoInterface<IScriptFile>::operator=(a1 + 136);
              }
              v25 = 3;
              if ( v42 > 0 )
                v25 = v42;
              if ( (_DWORD)v40 )
                CWxString::Transfer((CWxString *)&v39, (struct CWxString *)(a1 + 88));
              v26 = v47;
              v27 = *(_OWORD *)v48;
              *(_DWORD *)(a1 + 104) = a5;
              v28 = hObject;
              *(_OWORD *)(a1 + 32) = v26;
              *(_QWORD *)(a1 + 112) = v28;
              v29 = (__int64)v10;
              v30 = v49;
              *(_QWORD *)(a1 + 16) = v10;
              v10 = 0;
              *(_OWORD *)(a1 + 48) = v27;
              hObject = 0;
              *(_QWORD *)&v27 = v50;
              *(_OWORD *)(a1 + 64) = v30;
              *(_DWORD *)(a1 + 24) = v25;
              *(_QWORD *)(a1 + 80) = v27;
              v47 = 0;
              v50 = 0;
              *(_OWORD *)v48 = 0;
              v49 = 0;
              if ( (xmmword_180107A60 & 0x20) != 0 )
                WPP_SF_qS(1029, 23, (unsigned int)WPP_ca560ec3f10535b7d2ca7712797057c8_Traceguids, a1, v29);
            }
LABEL_43:
            v31 = v21;
LABEL_44:
            v8 = v39;
            goto LABEL_45;
          }
          HIDWORD(v37) = 541;
        }
        v31 = v22;
        goto LABEL_44;
      }
      HIDWORD(v37) = 533;
      goto LABEL_43;
    }
    v31 = -2147024809;
    HIDWORD(v37) = 531;
    v21 = -2147024809;
  }
  else
  {
    v31 = -2147024809;
    HIDWORD(v37) = 517;
    v21 = -2147024809;
  }
LABEL_45:
  FreeProxyConfigInfo<WxCoTaskAllocator>((int *)&v47);
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 24, WPP_ca560ec3f10535b7d2ca7712797057c8_Traceguids, (unsigned int)v21, *(_QWORD *)dwDesiredAccess);
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(struct IProxyDetectionHandle *))(*(_QWORD *)v11 + 16LL))(v11);
  hSourceHandle = v8;
  if ( v8 != qword_1800E7D10 && v8 )
    WxFreeHeapEx(&hSourceHandle);
  if ( v10 )
    CoTaskMemFree(v10);
  return v31;
}

```

## disassembly

```asm
0x18000a954  mov     [rsp-8+arg_10], rbx
0x18000a959  push    rbp
0x18000a95a  push    rsi
0x18000a95b  push    rdi
0x18000a95c  push    r12
0x18000a95e  push    r13
0x18000a960  push    r14
0x18000a962  push    r15
0x18000a964  lea     rbp, [rsp-0Fh]
0x18000a969  sub     rsp, 0F0h
0x18000a970  mov     rax, cs:__security_cookie
0x18000a977  xor     rax, rsp
0x18000a97a  mov     [rbp+3Fh+var_38], rax
0x18000a97e  xor     r15d, r15d
0x18000a981  mov     [rbp+3Fh+var_90], rdx
0x18000a985  xorps   xmm0, xmm0
0x18000a988  mov     [rbp+3Fh+var_80], r9
0x18000a98c  xor     eax, eax
0x18000a98e  mov     [rbp+3Fh+var_98], r8d
0x18000a992  mov     r13, rcx
0x18000a995  mov     dword ptr [rbp+3Fh+var_C0+4], r15d
0x18000a999  mov     rcx, [rbp+3Fh+arg_30]
0x18000a99d  lea     r12, qword_1800E7D10
0x18000a9a4  mov     [rbp+3Fh+var_88], rcx
0x18000a9a8  mov     rbx, rdx
0x18000a9ab  mov     rdx, [rbp+3Fh+arg_28]
0x18000a9af  mov     esi, r15d
0x18000a9b2  mov     [rbp+3Fh+hSourceHandle], rdx
0x18000a9b6  mov     edi, r15d
0x18000a9b9  mov     [rbp+3Fh+var_40], rax
0x18000a9bd  mov     [rbp+3Fh+var_B0], r12
0x18000a9c1  mov     [rbp+3Fh+var_A8], r15
0x18000a9c5  mov     [rbp+3Fh+hObject], r15
0x18000a9c9  movups  [rbp+3Fh+var_70], xmm0
0x18000a9cd  movups  xmmword ptr [rbp+3Fh+var_60], xmm0
0x18000a9d1  movups  [rbp+3Fh+var_50], xmm0
0x18000a9d5  test    rcx, rcx
0x18000a9d8  jz      loc_18000ACF4
0x18000a9de  test    byte ptr cs:xmmword_180107A60, 20h
0x18000a9e5  jnz     loc_18000AD63
0x18000a9eb  test    rbx, rbx
0x18000a9ee  jz      loc_18000ADA2
0x18000a9f4  mov     [rbp+3Fh+var_9C], r15d
0x18000a9f8  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000a9fc  inc     r14
0x18000a9ff  cmp     [rbx+r14*2], r15w
0x18000aa04  jnz     short loc_18000A9FC
0x18000aa06  lea     eax, ds:2[r14*2]
0x18000aa0e  mov     [rbp+3Fh+var_9C], r15d
0x18000aa12  mov     rbx, r15
0x18000aa15  mov     ecx, eax; cb
0x18000aa17  mov     [rsp+60h], rbx
0x18000aa1c  mov     r15d, eax
0x18000aa1f  call    cs:__imp_CoTaskMemAlloc
0x18000aa25  mov     r12, rax
0x18000aa28  test    rax, rax
0x18000aa2b  jz      loc_18000ACC0
0x18000aa31  mov     r8d, r15d; Size
0x18000aa34  xor     edx, edx; Val
0x18000aa36  mov     rcx, rax; void *
0x18000aa39  call    memset_0
0x18000aa3e  mov     rbx, r12
0x18000aa41  mov     [rsp+60h], rbx
0x18000aa46  lea     eax, [r14+1]
0x18000aa4a  xor     r9d, r9d
0x18000aa4d  mov     edx, eax
0x18000aa4f  mov     r15d, 80070057h
0x18000aa55  test    eax, eax
0x18000aa57  jz      loc_18000AD15
0x18000aa5d  cmp     rdx, 7FFFFFFFh
0x18000aa64  ja      loc_18000AD20
0x18000aa6a  mov     rax, [rbp+3Fh+var_90]
0x18000aa6e  mov     ecx, 7FFFFFFEh
0x18000aa73  test    rcx, rcx
0x18000aa76  jz      short loc_18000AA98
0x18000aa78  movzx   r8d, word ptr [rax]
0x18000aa7c  test    r8w, r8w
0x18000aa80  jz      short loc_18000AA98
0x18000aa82  mov     [r12], r8w
0x18000aa87  add     rax, 2
0x18000aa8b  add     r12, 2
0x18000aa8f  dec     rcx
0x18000aa92  sub     rdx, 1
0x18000aa96  jnz     short loc_18000AA73
0x18000aa98  test    rdx, rdx
0x18000aa9b  lea     rcx, [r12-2]
0x18000aaa0  cmovnz  rcx, r12
0x18000aaa4  neg     rdx
0x18000aaa7  sbb     r14d, r14d
0x18000aaaa  not     r14d
0x18000aaad  and     r14d, 8007007Ah
0x18000aab4  mov     [rcx], r9w
0x18000aab8  test    r14d, r14d
0x18000aabb  js      loc_18000AD28
0x18000aac1  mov     rsi, rbx
0x18000aac4  mov     rbx, r9
0x18000aac7  mov     [rsp+60h], rbx
0x18000aacc  xor     r15d, r15d
0x18000aacf  test    rbx, rbx
0x18000aad2  jnz     loc_18000AC8F
0x18000aad8  test    r14d, r14d
0x18000aadb  js      loc_18000AD09
0x18000aae1  mov     rdx, [rbp+3Fh+var_88]; struct _PROXY_CONFIG_INFO *
0x18000aae5  lea     r8, [rbp+3Fh+var_70]; struct _PROXY_CONFIG_INFO *
0x18000aae9  xor     ecx, ecx; void *
0x18000aaeb  call    ?WxCopyProxyConfigInfo@@YAJPEAXPEBU_PROXY_CONFIG_INFO@@PEAU1@@Z; WxCopyProxyConfigInfo(void *,_PROXY_CONFIG_INFO const *,_PROXY_CONFIG_INFO *)
0x18000aaf0  mov     r14d, eax
0x18000aaf3  test    eax, eax
0x18000aaf5  js      loc_18000ADB7
0x18000aafb  mov     rdx, [rbp+3Fh+var_80]; unsigned __int16 *
0x18000aaff  test    rdx, rdx
0x18000ab02  jz      short loc_18000AB18
0x18000ab04  lea     rcx, [rbp+3Fh+var_B0]; this
0x18000ab08  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x18000ab0d  mov     r14d, eax
0x18000ab10  test    eax, eax
0x18000ab12  js      loc_18000ACE5
0x18000ab18  mov     r14, [rbp+3Fh+hSourceHandle]
0x18000ab1c  test    r14, r14
0x18000ab1f  jnz     loc_18000ADC3
0x18000ab25  mov     rbx, r15
0x18000ab28  mov     dword ptr [rbp+3Fh+hSourceHandle+4], r15d
0x18000ab2c  mov     [rsp+60h], rbx
0x18000ab31  test    byte ptr cs:xmmword_180107A60, 20h
0x18000ab38  jnz     loc_18000AE33
0x18000ab3e  mov     rcx, [rbp+3Fh+var_60]; hSourceHandle
0x18000ab42  test    rcx, rcx
0x18000ab45  jnz     loc_18000AE51
0x18000ab4b  mov     r14d, r15d
0x18000ab4e  test    byte ptr cs:xmmword_180107A60, 20h
0x18000ab55  jnz     loc_18000AE7D
0x18000ab5b  test    rbx, rbx
0x18000ab5e  jz      short loc_18000AB6F
0x18000ab60  mov     rax, [rbx]
0x18000ab63  mov     rcx, rbx
0x18000ab66  mov     rax, [rax+10h]
0x18000ab6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab6f  test    r14d, r14d
0x18000ab72  js      loc_18000ACD9
0x18000ab78  test    rdi, rdi
0x18000ab7b  jnz     loc_18000AE9B
0x18000ab81  mov     eax, [rbp+3Fh+var_98]
0x18000ab84  mov     ebx, 3
0x18000ab89  test    eax, eax
0x18000ab8b  cmovg   ebx, eax
0x18000ab8e  cmp     dword ptr [rbp+3Fh+var_A8], r15d
0x18000ab92  jnz     loc_18000ACAE
0x18000ab98  movups  xmm0, [rbp+3Fh+var_70]
0x18000ab9c  mov     eax, [rbp+3Fh+arg_20]
0x18000ab9f  xor     ecx, ecx
0x18000aba1  movups  xmm1, xmmword ptr [rbp+3Fh+var_60]
0x18000aba5  mov     [r13+68h], eax
0x18000aba9  mov     rax, [rbp+3Fh+hObject]
0x18000abad  movups  xmmword ptr [r13+20h], xmm0
0x18000abb2  mov     [r13+70h], rax
0x18000abb6  mov     rax, rsi
0x18000abb9  movups  xmm0, [rbp+3Fh+var_50]
0x18000abbd  mov     [r13+10h], rsi
0x18000abc1  mov     rsi, r15
0x18000abc4  movups  xmmword ptr [r13+30h], xmm1
0x18000abc9  mov     [rbp+3Fh+hObject], r15
0x18000abcd  movsd   xmm1, [rbp+3Fh+var_40]
0x18000abd2  movups  xmmword ptr [r13+40h], xmm0
0x18000abd7  mov     [r13+18h], ebx
0x18000abdb  xorps   xmm0, xmm0
0x18000abde  movsd   qword ptr [r13+50h], xmm1
0x18000abe4  movups  [rbp+3Fh+var_70], xmm0
0x18000abe8  mov     [rbp+3Fh+var_40], rcx
0x18000abec  movups  xmmword ptr [rbp+3Fh+var_60], xmm0
0x18000abf0  movups  [rbp+3Fh+var_50], xmm0
0x18000abf4  test    byte ptr cs:xmmword_180107A60, 20h
0x18000abfb  jnz     loc_18000AEB9
0x18000ac01  mov     r15d, r14d
0x18000ac04  mov     r12, [rbp+3Fh+var_B0]
0x18000ac08  lea     rcx, [rbp+3Fh+var_70]
0x18000ac0c  call    ??$FreeProxyConfigInfo@VWxCoTaskAllocator@@@@YAXPEAU_PROXY_CONFIG_INFO@@@Z; FreeProxyConfigInfo<WxCoTaskAllocator>(_PROXY_CONFIG_INFO *)
0x18000ac11  test    byte ptr cs:xmmword_180107A60, 20h
0x18000ac18  jnz     loc_18000AEDC
0x18000ac1e  mov     rcx, [rbp+3Fh+hObject]; hObject
0x18000ac22  xor     ebx, ebx
0x18000ac24  test    rcx, rcx
0x18000ac27  jz      short loc_18000AC33
0x18000ac29  call    cs:__imp_CloseHandle
0x18000ac2f  mov     [rbp+3Fh+hObject], rbx
0x18000ac33  test    rdi, rdi
0x18000ac36  jz      short loc_18000AC47
0x18000ac38  mov     rax, [rdi]
0x18000ac3b  mov     rcx, rdi
0x18000ac3e  mov     rax, [rax+10h]
0x18000ac42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac47  lea     rax, qword_1800E7D10
0x18000ac4e  mov     [rbp+3Fh+hSourceHandle], r12
0x18000ac52  cmp     r12, rax
0x18000ac55  jnz     short loc_18000AC9E
0x18000ac57  test    rsi, rsi
0x18000ac5a  jz      short loc_18000AC65
0x18000ac5c  mov     rcx, rsi; pv
0x18000ac5f  call    cs:__imp_CoTaskMemFree
0x18000ac65  mov     eax, r15d
0x18000ac68  mov     rcx, [rbp+3Fh+var_38]
0x18000ac6c  xor     rcx, rsp; StackCookie
0x18000ac6f  call    __security_check_cookie
0x18000ac74  mov     rbx, [rsp+120h+arg_10]
0x18000ac7c  add     rsp, 0F0h
0x18000ac83  pop     r15
0x18000ac85  pop     r14
0x18000ac87  pop     r13
0x18000ac89  pop     r12
0x18000ac8b  pop     rdi
0x18000ac8c  pop     rsi
0x18000ac8d  pop     rbp
0x18000ac8e  retn
0x18000ac8f  lea     rcx, [rsp+120h+var_C0]; void **
0x18000ac94  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x18000ac99  jmp     loc_18000AAD8
0x18000ac9e  test    r12, r12
0x18000aca1  jz      short loc_18000AC57
0x18000aca3  lea     rcx, [rbp+3Fh+hSourceHandle]
0x18000aca7  call    WxFreeHeapEx
0x18000acac  jmp     short loc_18000AC57
0x18000acae  lea     rdx, [r13+58h]; struct CWxString *
0x18000acb2  lea     rcx, [rbp+3Fh+var_B0]; this
0x18000acb6  call    ?Transfer@CWxString@@QEAAXPEAV1@@Z; CWxString::Transfer(CWxString *)
0x18000acbb  jmp     loc_18000AB98
0x18000acc0  mov     [rbp+3Fh+var_9C], 4Ch ; 'L'
0x18000acc7  mov     r14d, 8007000Eh
0x18000accd  mov     [rbp+3Fh+var_9C], 220h
0x18000acd4  jmp     loc_18000AACC
0x18000acd9  mov     dword ptr [rbp+3Fh+var_C0+4], 232h
0x18000ace0  jmp     loc_18000AC01
0x18000ace5  mov     dword ptr [rbp+3Fh+var_C0+4], 21Dh
0x18000acec  mov     r15d, eax
0x18000acef  jmp     loc_18000AC04
0x18000acf4  mov     r15d, 80070057h
0x18000acfa  mov     dword ptr [rbp+3Fh+var_C0+4], 205h
0x18000ad01  mov     r14d, r15d
0x18000ad04  jmp     loc_18000AC08
0x18000ad09  mov     dword ptr [rbp+3Fh+var_C0+4], 215h
0x18000ad10  jmp     loc_18000AC01
0x18000ad15  mov     r14d, r15d
0x18000ad18  test    eax, eax
0x18000ad1a  jz      loc_18000AAB8
0x18000ad20  mov     [r12], r9w
0x18000ad25  mov     r14d, r15d
0x18000ad28  mov     [rbp+3Fh+var_9C], 224h
0x18000ad2f  jmp     loc_18000AACC
0x18000ad34  call    cs:__imp_GetLastError
0x18000ad3a  mov     r14d, eax
0x18000ad3d  test    eax, eax
0x18000ad3f  jle     short loc_18000AD4C
0x18000ad41  movzx   r14d, ax
0x18000ad45  or      r14d, 80070000h
0x18000ad4c  test    r14d, r14d
0x18000ad4f  js      short loc_18000AD57
0x18000ad51  mov     r14d, 8000FFFFh
0x18000ad57  mov     dword ptr [rbp+3Fh+var_C0+4], 228h
0x18000ad5e  jmp     loc_18000AC01
0x18000ad63  mov     eax, [rcx+24h]
0x18000ad66  mov     [rsp+120h+var_C8], eax
0x18000ad6a  mov     rax, [rcx+10h]
0x18000ad6e  mov     [rsp+120h+var_D0], rax
0x18000ad73  mov     eax, [rcx+18h]
0x18000ad76  mov     [rsp+120h+var_D8], eax
0x18000ad7a  mov     eax, [rbp+3Fh+arg_20]
0x18000ad7d  mov     [rsp+120h+var_E0], eax
0x18000ad81  mov     [rsp+120h+var_E8], rdx
0x18000ad86  mov     qword ptr [rsp+120h+dwOptions], r9
0x18000ad8b  mov     r9, r13
0x18000ad8e  mov     [rsp+120h+bInheritHandle], r8d
0x18000ad93  mov     qword ptr [rsp+120h+dwDesiredAccess], rbx
0x18000ad98  call    WPP_SF_qSDSqDDqD
0x18000ad9d  jmp     loc_18000A9EB
0x18000ada2  mov     r15d, 80070057h
0x18000ada8  mov     dword ptr [rbp+3Fh+var_C0+4], 213h
0x18000adaf  mov     r14d, r15d
0x18000adb2  jmp     loc_18000AC08
0x18000adb7  mov     dword ptr [rbp+3Fh+var_C0+4], 219h
0x18000adbe  jmp     loc_18000ACEC
0x18000adc3  call    cs:__imp_GetCurrentProcess
0x18000adc9  mov     rbx, rax
0x18000adcc  call    cs:__imp_GetCurrentProcess
0x18000add2  mov     [rsp+120h+dwOptions], 2; dwOptions
0x18000adda  lea     r9, [rbp+3Fh+hObject]; lpTargetHandle
0x18000adde  mov     rcx, rax; hSourceProcessHandle
0x18000ade1  mov     [rsp+120h+bInheritHandle], r15d; bInheritHandle
0x18000ade6  mov     r8, rbx; hTargetProcessHandle
0x18000ade9  mov     [rsp+120h+dwDesiredAccess], r15d; dwDesiredAccess
0x18000adee  mov     rdx, r14; hSourceHandle
0x18000adf1  call    cs:__imp_DuplicateHandle
0x18000adf7  test    eax, eax
0x18000adf9  jz      loc_18000AD34
0x18000adff  test    byte ptr cs:xmmword_180107A60, 20h
0x18000ae06  jz      loc_18000AB25
0x18000ae0c  mov     rax, [rbp+3Fh+hObject]
0x18000ae10  lea     r8, WPP_ca560ec3f10535b7d2ca7712797057c8_Traceguids
0x18000ae17  mov     edx, 16h
0x18000ae1c  mov     qword ptr [rsp+120h+dwDesiredAccess], rax
0x18000ae21  mov     ecx, 405h
0x18000ae26  mov     r9, r14
0x18000ae29  call    WPP_SF_qq
  ... truncated ...
```
