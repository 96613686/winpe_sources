# Windows::Internal::CloudRequestor::Common::ClientInfoUtils::BuildClientInfoHeaderString(void)

- ea: `0x18006dd44`
- end: `0x18006e163`
- name: `?BuildClientInfoHeaderString@ClientInfoUtils@Common@CloudRequestor@Internal@Windows@@YA?AUhstring@winrt@@XZ`
- size: `1055`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180066cf8`
- `0x180069b64`

## callees

- `0x180002810`
- `0x1800034f7`
- `0x1800035ab`
- `0x18000d3b4`
- `0x18000e4a4`
- `0x18000ebfc`
- `0x18000f44c`
- `0x180067af8`
- `0x18006dd44`
- `0x18006e16c`
- `0x18006e2a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006df3d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006e061`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006e06c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006e077`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006e082`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006e147`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006df3d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006e061`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006e06c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006e077`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006e082`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006e147`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18006dde9`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18006de1f`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18006dde9`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18006de1f`

## string_xrefs

- `0x18006de65`: `onecoreuap\shell\clouddirect\common\clientinfoutils.cpp`
- `0x18006e151`: `onecoreuap\shell\clouddirect\common\clientinfoutils.cpp`
- `0x18006dd7d`: `SystemProductName`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct winrt::impl::shared_hstring_header **__fastcall Windows::Internal::CloudRequestor::Common::ClientInfoUtils::BuildClientInfoHeaderString(
        struct winrt::impl::shared_hstring_header **a1)
{
  struct winrt::impl::shared_hstring_header *v1; // r14
  volatile signed __int32 *v2; // rdi
  const WCHAR *v3; // r13
  volatile signed __int32 *v4; // rbx
  struct winrt::impl::shared_hstring_header *v5; // rcx
  int v6; // eax
  unsigned int v7; // edx
  __int64 v8; // rsi
  struct winrt::impl::shared_hstring_header *v9; // r15
  unsigned int v10; // eax
  const void *v11; // rsi
  int v12; // eax
  HANDLE ProcessHeap; // rax
  int v14; // eax
  unsigned int v15; // edx
  int v16; // eax
  HANDLE v17; // rax
  void *v18; // rsi
  int v19; // eax
  HANDLE v20; // rax
  int v21; // eax
  HANDLE v22; // rax
  int v23; // eax
  HANDLE v24; // rax
  __int64 v25; // rbx
  struct winrt::impl::shared_hstring_header *v26; // rdi
  struct winrt::impl::shared_hstring_header *v27; // rsi
  unsigned int v28; // r14d
  const void *v29; // rbx
  struct winrt::impl::shared_hstring_header **v30; // rbx
  int v31; // r12d
  HANDLE v32; // rax
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+40h] [rbp-C0h] BYREF
  struct winrt::impl::shared_hstring_header *v37; // [rsp+48h] [rbp-B8h]
  const WCHAR *v38; // [rsp+50h] [rbp-B0h]
  const WCHAR *v39; // [rsp+58h] [rbp-A8h]
  int v40[2]; // [rsp+60h] [rbp-A0h]
  LPVOID lpMem; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v42[2]; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v43; // [rsp+80h] [rbp-80h] BYREF
  struct winrt::impl::shared_hstring_header **v44; // [rsp+88h] [rbp-78h]
  __int64 v45; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 Source[512]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v47[512]; // [rsp+4A0h] [rbp+3A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8F8h] [rbp+7F8h]

  v44 = a1;
  v42[0] = a1;
  v1 = 0;
  Windows::Internal::CloudRequestor::Common::ClientInfoUtils::GetRegistryDeviceNames(&v43, L"SystemProductName");
  v2 = (volatile signed __int32 *)v43;
  v3 = &Name;
  if ( v43 )
    v38 = (const WCHAR *)*((_QWORD *)v43 + 2);
  else
    v38 = &Name;
  Windows::Internal::CloudRequestor::Common::ClientInfoUtils::GetRegistryDeviceNames(v42, L"SystemManufacturer");
  v4 = (volatile signed __int32 *)v42[0];
  if ( v42[0] )
    v39 = (const WCHAR *)*((_QWORD *)v42[0] + 2);
  else
    v39 = &Name;
  v36 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v36, 0);
  v5 = *Windows::Internal::CloudRequestor::Common::ClientInfoUtils::GetOsLocale((struct winrt::impl::shared_hstring_header **)&lpMem);
  if ( v5 )
    *(_QWORD *)v40 = *((_QWORD *)v5 + 2);
  else
    *(_QWORD *)v40 = &Name;
  v45 = 0;
  RtlGetDeviceFamilyInfoEnum(&v45, 0, 0);
  v34 = WORD2(v45);
  v6 = StringCchPrintfW(Source, 0x200u, L"%hu.%hu.%hu.%hu", HIWORD(v45));
  if ( v6 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\common\\clientinfoutils.cpp",
      (const char *)(unsigned int)v6,
      v34);
  v8 = -1;
  do
    ++v8;
  while ( Source[v8] );
  if ( (_DWORD)v8 )
  {
    v9 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v8, v7);
    memcpy_s((char *)v9 + 28, 2LL * (unsigned int)v8, Source, 2LL * (unsigned int)v8);
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    if ( (*(_BYTE *)v9 & 1) != 0 )
    {
      v10 = *((_DWORD *)v9 + 1);
      LODWORD(v37) = v10;
      if ( v10 )
      {
        v11 = (const void *)*((_QWORD *)v9 + 2);
        v1 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v10, v7);
        memcpy_s((char *)v1 + 28, 2LL * (unsigned int)v37, v11, 2LL * (unsigned int)v37);
      }
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)v9 + 6);
      v1 = v9;
    }
  }
  v37 = v1;
  if ( v9 )
  {
    v12 = _InterlockedDecrement((volatile signed __int32 *)v9 + 6);
    if ( v12 )
    {
      if ( v12 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v9);
    }
  }
  if ( v1 )
    v3 = (const WCHAR *)*((_QWORD *)v1 + 2);
  else
    v1 = 0;
  v14 = StringCchPrintfW(
          v47,
          0x200u,
          L"os=windows;osVer=%s;lcid=%s;deviceType=%lu;deviceModel=%s/%s;",
          v3,
          *(_QWORD *)v40,
          v36,
          v39,
          v38);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\common\\clientinfoutils.cpp",
      (const char *)(unsigned int)v14,
      v35);
  if ( v1 )
  {
    v16 = _InterlockedDecrement((volatile signed __int32 *)v1 + 6);
    if ( v16 )
    {
      if ( v16 < 0 )
        abort();
    }
    else
    {
      v17 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v17, 0, v1);
    }
  }
  v18 = lpMem;
  if ( lpMem )
  {
    v19 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v19 )
    {
      if ( v19 < 0 )
        abort();
    }
    else
    {
      v20 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v20, 0, v18);
    }
    lpMem = 0;
  }
  if ( v4 )
  {
    v21 = _InterlockedDecrement(v4 + 6);
    if ( v21 )
    {
      if ( v21 < 0 )
        abort();
    }
    else
    {
      v22 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v22, 0, (LPVOID)v4);
    }
  }
  if ( v2 )
  {
    v23 = _InterlockedDecrement(v2 + 6);
    if ( v23 )
    {
      if ( v23 < 0 )
        abort();
    }
    else
    {
      v24 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v24, 0, (LPVOID)v2);
    }
  }
  v25 = -1;
  do
    ++v25;
  while ( v47[v25] );
  if ( (_DWORD)v25 )
  {
    v26 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v25, v15);
    memcpy_s((char *)v26 + 28, 2LL * (unsigned int)v25, v47, 2LL * (unsigned int)v25);
  }
  else
  {
    v26 = 0;
  }
  if ( !v26 )
    goto LABEL_58;
  if ( (*(_BYTE *)v26 & 1) != 0 )
  {
    v28 = *((_DWORD *)v26 + 1);
    if ( !v28 )
    {
LABEL_58:
      v27 = 0;
      goto LABEL_63;
    }
    v29 = (const void *)*((_QWORD *)v26 + 2);
    v27 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v28, v15);
    memcpy_s((char *)v27 + 28, 2LL * v28, v29, 2LL * v28);
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)v26 + 6);
    v27 = v26;
  }
LABEL_63:
  v30 = v44;
  *v44 = v27;
  if ( v26 )
  {
    v31 = _InterlockedDecrement((volatile signed __int32 *)v26 + 6);
    if ( v31 )
    {
      if ( v31 < 0 )
        abort();
    }
    else
    {
      v32 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v32, 0, v26);
    }
  }
  return v30;
}

```

## disassembly

```asm
0x18006dd44  push    rbp
0x18006dd46  push    rbx
0x18006dd47  push    rsi
0x18006dd48  push    rdi
0x18006dd49  push    r12
0x18006dd4b  push    r13
0x18006dd4d  push    r14
0x18006dd4f  push    r15
0x18006dd51  lea     rbp, [rsp-7B8h]
0x18006dd59  sub     rsp, 8B8h
0x18006dd60  mov     rax, cs:__security_cookie
0x18006dd67  xor     rax, rsp
0x18006dd6a  mov     [rbp+7F0h+var_50], rax
0x18006dd71  mov     [rbp+7F0h+var_868], rcx
0x18006dd75  mov     [rsp+8F0h+var_880], rcx
0x18006dd7a  xor     r14d, r14d
0x18006dd7d  lea     rdx, aSystemproductn; "SystemProductName"
0x18006dd84  lea     rcx, [rbp+7F0h+var_870]
0x18006dd88  call    ?GetRegistryDeviceNames@ClientInfoUtils@Common@CloudRequestor@Internal@Windows@@YA?AUhstring@winrt@@PEBG@Z; Windows::Internal::CloudRequestor::Common::ClientInfoUtils::GetRegistryDeviceNames(ushort const *)
0x18006dd8d  nop
0x18006dd8e  mov     rdi, [rbp+7F0h+var_870]
0x18006dd92  lea     r13, Name
0x18006dd99  test    rdi, rdi
0x18006dd9c  jz      short loc_18006DDA9
0x18006dd9e  mov     rsi, [rdi+10h]
0x18006dda2  mov     [rsp+8F0h+var_8A0], rsi
0x18006dda7  jmp     short loc_18006DDAE
0x18006dda9  mov     [rsp+8F0h+var_8A0], r13
0x18006ddae  lea     rdx, aSystemmanufact; "SystemManufacturer"
0x18006ddb5  lea     rcx, [rsp+8F0h+var_880]
0x18006ddba  call    ?GetRegistryDeviceNames@ClientInfoUtils@Common@CloudRequestor@Internal@Windows@@YA?AUhstring@winrt@@PEBG@Z; Windows::Internal::CloudRequestor::Common::ClientInfoUtils::GetRegistryDeviceNames(ushort const *)
0x18006ddbf  nop
0x18006ddc0  mov     rbx, [rsp+8F0h+var_880]
0x18006ddc5  test    rbx, rbx
0x18006ddc8  jz      short loc_18006DDD5
0x18006ddca  mov     rsi, [rbx+10h]
0x18006ddce  mov     [rsp+8F0h+var_898], rsi
0x18006ddd3  jmp     short loc_18006DDDA
0x18006ddd5  mov     [rsp+8F0h+var_898], r13
0x18006ddda  mov     [rsp+8F0h+var_8B0], r14d
0x18006dddf  xor     r8d, r8d
0x18006dde2  lea     rdx, [rsp+8F0h+var_8B0]
0x18006dde7  xor     ecx, ecx
0x18006dde9  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18006ddef  lea     rcx, [rsp+8F0h+lpMem]
0x18006ddf4  call    ?GetOsLocale@ClientInfoUtils@Common@CloudRequestor@Internal@Windows@@YA?AUhstring@winrt@@XZ; Windows::Internal::CloudRequestor::Common::ClientInfoUtils::GetOsLocale(void)
0x18006ddf9  nop
0x18006ddfa  mov     rcx, [rax]
0x18006ddfd  test    rcx, rcx
0x18006de00  jz      short loc_18006DE0D
0x18006de02  mov     rsi, [rcx+10h]
0x18006de06  mov     qword ptr [rsp+8F0h+var_890], rsi
0x18006de0b  jmp     short loc_18006DE12
0x18006de0d  mov     qword ptr [rsp+8F0h+var_890], r13
0x18006de12  mov     [rbp+7F0h+var_860], r14
0x18006de16  xor     r8d, r8d
0x18006de19  xor     edx, edx
0x18006de1b  lea     rcx, [rbp+7F0h+var_860]
0x18006de1f  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18006de25  movzx   eax, word ptr [rbp+7F0h+var_860]
0x18006de29  movzx   ecx, word ptr [rbp+7F0h+var_860+2]
0x18006de2d  movzx   edx, word ptr [rbp+7F0h+var_860+4]
0x18006de31  movzx   r9d, word ptr [rbp+7F0h+var_860+6]
0x18006de36  mov     dword ptr [rsp+8F0h+var_8C0], eax
0x18006de3a  mov     [rsp+8F0h+var_8C8], ecx
0x18006de3e  mov     [rsp+8F0h+var_8D0], edx; int
0x18006de42  lea     r8, aHuHuHuHu; "%hu.%hu.%hu.%hu"
0x18006de49  mov     edx, 200h; unsigned __int64
0x18006de4e  lea     rcx, [rbp+7F0h+Source]; unsigned __int16 *
0x18006de52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006de57  mov     rcx, [rbp+7F8h]; this
0x18006de5e  test    eax, eax
0x18006de60  jns     short loc_18006DE76
0x18006de62  mov     r9d, eax; char *
0x18006de65  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\clouddirect\\common"...
0x18006de6c  mov     edx, 24h ; '$'; void *
0x18006de71  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006de76  lea     rax, [rbp+7F0h+Source]
0x18006de7a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18006de7e  mov     rsi, r12
0x18006de81  inc     rsi
0x18006de84  cmp     [rax+rsi*2], r14w
0x18006de89  jnz     short loc_18006DE81
0x18006de8b  test    esi, esi
0x18006de8d  jnz     short loc_18006DE94
0x18006de8f  mov     r15, r14
0x18006de92  jmp     short loc_18006DEB4
0x18006de94  mov     ecx, esi; this
0x18006de96  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18006de9b  mov     r15, rax
0x18006de9e  mov     edx, esi
0x18006dea0  add     rdx, rdx; DestinationSize
0x18006dea3  lea     rcx, [rax+1Ch]; Destination
0x18006dea7  mov     r9, rdx; SourceSize
0x18006deaa  lea     r8, [rbp+7F0h+Source]; Source
0x18006deae  call    memcpy_s
0x18006deb3  nop
0x18006deb4  test    r15, r15
0x18006deb7  jz      short loc_18006DEF9
0x18006deb9  test    byte ptr [r15], 1
0x18006debd  jnz     short loc_18006DEC9
0x18006debf  lock inc dword ptr [r15+18h]
0x18006dec4  mov     r14, r15
0x18006dec7  jmp     short loc_18006DEF9
0x18006dec9  mov     eax, [r15+4]
0x18006decd  mov     dword ptr [rsp+8F0h+var_8A8], eax
0x18006ded1  test    eax, eax
0x18006ded3  jz      short loc_18006DEF9
0x18006ded5  mov     rsi, [r15+10h]
0x18006ded9  mov     ecx, eax; this
0x18006dedb  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18006dee0  mov     r14, rax
0x18006dee3  mov     edx, dword ptr [rsp+8F0h+var_8A8]
0x18006dee7  add     rdx, rdx; DestinationSize
0x18006deea  lea     rcx, [rax+1Ch]; Destination
0x18006deee  mov     r9, rdx; SourceSize
0x18006def1  mov     r8, rsi; Source
0x18006def4  call    memcpy_s
0x18006def9  mov     [rsp+8F0h+var_8A8], r14
0x18006defe  test    r15, r15
0x18006df01  jz      short loc_18006DF24
0x18006df03  mov     eax, r12d
0x18006df06  lock xadd [r15+18h], eax
0x18006df0c  sub     eax, 1
0x18006df0f  jnz     short loc_18006DF36
0x18006df11  nop
0x18006df12  call    WINRT_IMPL_GetProcessHeap
0x18006df17  mov     rcx, rax; hHeap
0x18006df1a  mov     r8, r15; lpMem
0x18006df1d  xor     edx, edx; dwFlags
0x18006df1f  call    WINRT_IMPL_HeapFree
0x18006df24  xor     r15d, r15d
0x18006df27  mov     eax, [rsp+8F0h+var_8B0]
0x18006df2b  test    r14, r14
0x18006df2e  jz      short loc_18006DF44
0x18006df30  mov     r13, [r14+10h]
0x18006df34  jmp     short loc_18006DF47
0x18006df36  xor     r15d, r15d
0x18006df39  test    eax, eax
0x18006df3b  jns     short loc_18006DF27
0x18006df3d  call    cs:__imp_abort
0x18006df44  mov     r14, r15
0x18006df47  mov     rcx, [rsp+8F0h+var_8A0]
0x18006df4c  mov     [rsp+8F0h+var_8B8], rcx
0x18006df51  mov     rcx, [rsp+8F0h+var_898]
0x18006df56  mov     [rsp+8F0h+var_8C0], rcx
0x18006df5b  mov     [rsp+8F0h+var_8C8], eax
0x18006df5f  mov     rax, qword ptr [rsp+8F0h+var_890]
0x18006df64  mov     qword ptr [rsp+8F0h+var_8D0], rax; int
0x18006df69  mov     r9, r13
0x18006df6c  lea     r8, aOsWindowsOsver; "os=windows;osVer=%s;lcid=%s;deviceType="...
0x18006df73  mov     edx, 200h; unsigned __int64
0x18006df78  lea     rcx, [rbp+7F0h+var_450]; unsigned __int16 *
0x18006df7f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006df84  mov     rcx, [rbp+7F8h]; this
0x18006df8b  test    eax, eax
0x18006df8d  js      loc_18006E14E
0x18006df93  test    r14, r14
0x18006df96  jz      short loc_18006DFBE
0x18006df98  mov     eax, r12d
0x18006df9b  lock xadd [r14+18h], eax
0x18006dfa1  sub     eax, 1
0x18006dfa4  jnz     loc_18006E059
0x18006dfaa  nop
0x18006dfab  call    WINRT_IMPL_GetProcessHeap
0x18006dfb0  mov     rcx, rax; hHeap
0x18006dfb3  mov     r8, r14; lpMem
0x18006dfb6  xor     edx, edx; dwFlags
0x18006dfb8  call    WINRT_IMPL_HeapFree
0x18006dfbd  nop
0x18006dfbe  mov     rsi, [rsp+8F0h+lpMem]
0x18006dfc3  test    rsi, rsi
0x18006dfc6  jz      short loc_18006DFF1
0x18006dfc8  mov     eax, r12d
0x18006dfcb  lock xadd [rsi+18h], eax
0x18006dfd0  sub     eax, 1
0x18006dfd3  jnz     loc_18006E068
0x18006dfd9  nop
0x18006dfda  call    WINRT_IMPL_GetProcessHeap
0x18006dfdf  mov     rcx, rax; hHeap
0x18006dfe2  mov     r8, rsi; lpMem
0x18006dfe5  xor     edx, edx; dwFlags
0x18006dfe7  call    WINRT_IMPL_HeapFree
0x18006dfec  mov     [rsp+8F0h+lpMem], r15
0x18006dff1  test    rbx, rbx
0x18006dff4  jz      short loc_18006E017
0x18006dff6  mov     eax, r12d
0x18006dff9  lock xadd [rbx+18h], eax
0x18006dffe  sub     eax, 1
0x18006e001  jnz     short loc_18006E073
0x18006e003  nop
0x18006e004  call    WINRT_IMPL_GetProcessHeap
0x18006e009  mov     rcx, rax; hHeap
0x18006e00c  mov     r8, rbx; lpMem
0x18006e00f  xor     edx, edx; dwFlags
0x18006e011  call    WINRT_IMPL_HeapFree
0x18006e016  nop
0x18006e017  test    rdi, rdi
0x18006e01a  jz      short loc_18006E03C
0x18006e01c  mov     eax, r12d
0x18006e01f  lock xadd [rdi+18h], eax
0x18006e024  sub     eax, 1
0x18006e027  jnz     short loc_18006E07E
0x18006e029  nop
0x18006e02a  call    WINRT_IMPL_GetProcessHeap
0x18006e02f  mov     rcx, rax; hHeap
0x18006e032  mov     r8, rdi; lpMem
0x18006e035  xor     edx, edx; dwFlags
0x18006e037  call    WINRT_IMPL_HeapFree
0x18006e03c  lea     rax, [rbp+7F0h+var_450]
0x18006e043  mov     rbx, r12
0x18006e046  inc     rbx
0x18006e049  cmp     [rax+rbx*2], r15w
0x18006e04e  jnz     short loc_18006E046
0x18006e050  test    ebx, ebx
0x18006e052  jnz     short loc_18006E089
0x18006e054  mov     rdi, r15
0x18006e057  jmp     short loc_18006E0AC
0x18006e059  test    eax, eax
0x18006e05b  jns     loc_18006DFBE
0x18006e061  call    cs:__imp_abort
0x18006e068  test    eax, eax
0x18006e06a  jns     short loc_18006DFEC
0x18006e06c  call    cs:__imp_abort
0x18006e073  test    eax, eax
0x18006e075  jns     short loc_18006E017
0x18006e077  call    cs:__imp_abort
0x18006e07e  test    eax, eax
0x18006e080  jns     short loc_18006E03C
0x18006e082  call    cs:__imp_abort
0x18006e089  mov     ecx, ebx; this
0x18006e08b  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18006e090  mov     rdi, rax
0x18006e093  mov     edx, ebx
0x18006e095  add     rdx, rdx; DestinationSize
0x18006e098  lea     rcx, [rax+1Ch]; Destination
0x18006e09c  mov     r9, rdx; SourceSize
0x18006e09f  lea     r8, [rbp+7F0h+var_450]; Source
0x18006e0a6  call    memcpy_s
0x18006e0ab  nop
0x18006e0ac  test    rdi, rdi
0x18006e0af  jnz     short loc_18006E0B6
0x18006e0b1  mov     rsi, r15
0x18006e0b4  jmp     short loc_18006E0F1
0x18006e0b6  test    byte ptr [rdi], 1
0x18006e0b9  jnz     short loc_18006E0C4
0x18006e0bb  lock inc dword ptr [rdi+18h]
0x18006e0bf  mov     rsi, rdi
0x18006e0c2  jmp     short loc_18006E0F1
0x18006e0c4  mov     r14d, [rdi+4]
0x18006e0c8  test    r14d, r14d
0x18006e0cb  jz      short loc_18006E0B1
0x18006e0cd  mov     rbx, [rdi+10h]
0x18006e0d1  mov     ecx, r14d; this
0x18006e0d4  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18006e0d9  mov     rsi, rax
0x18006e0dc  mov     edx, r14d
0x18006e0df  add     rdx, rdx; DestinationSize
0x18006e0e2  lea     rcx, [rax+1Ch]; Destination
0x18006e0e6  mov     r9, rdx; SourceSize
0x18006e0e9  mov     r8, rbx; Source
0x18006e0ec  call    memcpy_s
0x18006e0f1  mov     rbx, [rbp+7F0h+var_868]
0x18006e0f5  mov     [rbx], rsi
0x18006e0f8  test    rdi, rdi
0x18006e0fb  jz      short loc_18006E11C
0x18006e0fd  lock xadd [rdi+18h], r12d
0x18006e103  sub     r12d, 1
0x18006e107  jnz     short loc_18006E142
0x18006e109  nop
0x18006e10a  call    WINRT_IMPL_GetProcessHeap
0x18006e10f  mov     rcx, rax; hHeap
0x18006e112  mov     r8, rdi; lpMem
0x18006e115  xor     edx, edx; dwFlags
0x18006e117  call    WINRT_IMPL_HeapFree
0x18006e11c  mov     rax, rbx
0x18006e11f  mov     rcx, [rbp+7F0h+var_50]
0x18006e126  xor     rcx, rsp; StackCookie
0x18006e129  call    __security_check_cookie
0x18006e12e  add     rsp, 8B8h
0x18006e135  pop     r15
0x18006e137  pop     r14
0x18006e139  pop     r13
0x18006e13b  pop     r12
0x18006e13d  pop     rdi
0x18006e13e  pop     rsi
0x18006e13f  pop     rbx
0x18006e140  pop     rbp
0x18006e141  retn
0x18006e142  test    r12d, r12d
0x18006e145  jns     short loc_18006E11C
0x18006e147  call    cs:__imp_abort
0x18006e14e  mov     r9d, eax; char *
0x18006e151  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\clouddirect\\common"...
0x18006e158  mov     edx, 5Fh ; '_'; void *
0x18006e15d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
