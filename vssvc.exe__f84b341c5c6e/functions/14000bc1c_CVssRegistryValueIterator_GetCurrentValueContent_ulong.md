# CVssRegistryValueIterator::GetCurrentValueContent(ulong &)

- ea: `0x14000bc1c`
- end: `0x14000c09a`
- name: `?GetCurrentValueContent@CVssRegistryValueIterator@@QEAAXAEAK@Z`
- size: `1150`
- prototype: `void __fastcall(CVssRegistryValueIterator *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14002b160`

## callees

- `0x140006020`
- `0x14000bc1c`
- `0x14000dcd0`
- `0x1400137c0`
- `0x140013cb0`
- `0x140049ec4`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14000bed2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14000bed2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000bcc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000bcc3`
- `VssTrace!__imp_VssTraceMessage` at `0x14000bd82`
- `VssTrace!__imp_VssTraceMessage` at `0x14000bd82`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000bd04`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000bd04`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000bcf6`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000bcf6`

## string_xrefs

- `0x14000bc4a`: `CVssRegistryValueIterator::GetCurrentValueContent`
- `0x14000bdac`: `CVssRegistryValueIterator::GetCurrentValueContent`
- `0x14000be17`: `CVssRegistryValueIterator::GetCurrentValueContent`
- `0x14000bf17`: `CVssRegistryValueIterator::GetCurrentValueContent`
- `0x14000bf8a`: `CVssRegistryValueIterator::GetCurrentValueContent`
- `0x14000c008`: `CVssRegistryValueIterator::GetCurrentValueContent`
- `0x14000bc3e`: `base\stor\vss\modules\registry\registry.cxx`
- `0x14000bf0b`: `base\stor\vss\modules\registry\registry.cxx`
- `0x14000bdee`: `Unexpected error: attempting to read a value of the wrong type`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssRegistryValueIterator::GetCurrentValueContent(CVssRegistryValueIterator *this, unsigned int *a2)
{
  int v4; // eax
  __int64 v5; // rcx
  int v6; // edi
  int v7; // edi
  LSTATUS v8; // eax
  unsigned int v9; // edi
  DWORD v10; // esi
  __int64 v11; // r14
  int v12; // r15d
  __int64 v13; // rbx
  int v14; // ebx
  DWORD v15; // edi
  LPDWORD lpReserved; // [rsp+20h] [rbp-E0h]
  LPDWORD lpReserveda; // [rsp+20h] [rbp-E0h]
  LPDWORD lpType; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbData; // [rsp+38h] [rbp-C8h]
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v22; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v23; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v24; // [rsp+70h] [rbp-90h]
  int v25; // [rsp+78h] [rbp-88h]
  int v26; // [rsp+7Ch] [rbp-84h]
  int v27; // [rsp+80h] [rbp-80h]
  _BYTE v28[120]; // [rsp+88h] [rbp-78h] BYREF
  int v29; // [rsp+100h] [rbp+0h]
  unsigned __int64 v30; // [rsp+110h] [rbp+10h] BYREF
  int v31; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v32; // [rsp+120h] [rbp+20h]
  const unsigned __int16 *v33; // [rsp+128h] [rbp+28h]
  unsigned int v34; // [rsp+130h] [rbp+30h]
  int v35; // [rsp+134h] [rbp+34h]
  const wchar_t *v36; // [rsp+138h] [rbp+38h]
  unsigned int v37; // [rsp+140h] [rbp+40h]
  DWORD TickCount; // [rsp+144h] [rbp+44h]
  int v39; // [rsp+148h] [rbp+48h]
  __int128 v40; // [rsp+150h] [rbp+50h]
  __int128 v41; // [rsp+160h] [rbp+60h]
  __int64 v42; // [rsp+170h] [rbp+70h]
  DWORD cchValueName; // [rsp+1C0h] [rbp+C0h] BYREF
  DWORD Type; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned int Data; // [rsp+1D8h] [rbp+D8h] BYREF

  v22 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v23 = L"CVssRegistryValueIterator::GetCurrentValueContent";
  v24 = L"REGREGSC";
  v25 = 955;
  v26 = 11;
  v27 = 255;
  v29 = 0x1000000;
  memset_0(v28, 0, sizeof(v28));
  v31 = 0;
  v36 = L"CVssRegistryValueIterator::GetCurrentValueContent";
  v32 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v33 = L"REGREGSC";
  v34 = 955;
  v35 = 11;
  TickCount = GetTickCount();
  v39 = 255;
  v30 = 0xFFFFFFFF00000000uLL;
  v42 = 0;
  v40 = 0;
  v41 = 0;
  v20 = 0;
  if ( (int)VssGetTracingContextPerThread(&v20) < 0 )
  {
    v5 = v42;
  }
  else
  {
    v4 = VssSetTracingContextPerThread(&v30);
    v5 = v42;
    if ( v4 >= 0 )
      v5 = v20;
    v42 = v5;
  }
  if ( v5 )
    v37 = *(_DWORD *)(v5 + 48) + 1;
  else
    v37 = 0;
  v6 = 160;
  if ( v39 != 255 )
    v6 = v39;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v30) )
    VssTraceMessage(v32, v33, v34, v37, v35, v36, L"ENTER", v6, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v22);
  CVssRegistryValueIterator::ReadCurrentValueDetails(this);
  if ( *((_DWORD *)this + 4) != 4 )
  {
    v22 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v23 = L"CVssRegistryValueIterator::GetCurrentValueContent";
    v24 = L"REGREGSC";
    v25 = 961;
    v26 = 11;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    CVssFunctionTracer::TranslateGenericError(
      &v30,
      &v22,
      2147549183LL,
      L"Unexpected error: attempting to read a value of the wrong type");
  }
  v7 = *((_DWORD *)this + 11);
  if ( v7 != 4 )
  {
    v22 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v23 = L"CVssRegistryValueIterator::GetCurrentValueContent";
    v24 = L"REGREGSC";
    v25 = 966;
    v26 = 11;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    LODWORD(lpReserved) = v7;
    CVssFunctionTracer::TranslateGenericError(
      &v30,
      &v22,
      2147549183LL,
      L"Unexpected error: unexpected DWORD size [%ld, %ld]",
      lpReserved,
      4);
  }
  Data = 0;
  cchValueName = *((_DWORD *)this + 10);
  Type = 0;
  cbData = 4;
  v8 = RegEnumValueW(
         *(HKEY *)this,
         *((_DWORD *)this + 3),
         *((LPWSTR *)this + 4),
         &cchValueName,
         0,
         &Type,
         (LPBYTE)&Data,
         &cbData);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 != 259 )
    {
      v10 = cchValueName;
      v11 = *((_QWORD *)this + 4);
      v12 = *((_DWORD *)this + 3);
      v13 = *(_QWORD *)this;
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      v22 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v23 = L"CVssRegistryValueIterator::GetCurrentValueContent";
      v24 = L"REGREGSC";
      v25 = 997;
      v26 = 11;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      LODWORD(lpcbData) = v10;
      LODWORD(lpType) = v12;
      CVssFunctionTracer::TranslateGenericError(
        &v30,
        &v22,
        v9,
        L"RegEnumValue(%p,%lu,%p,%lu ...)",
        v13,
        lpType,
        v11,
        lpcbData);
    }
    v22 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v23 = L"CVssRegistryValueIterator::GetCurrentValueContent";
    v24 = L"REGREGSC";
    v25 = 995;
    v26 = 11;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    LODWORD(lpType) = *((_DWORD *)this + 2);
    LODWORD(lpReserveda) = *((_DWORD *)this + 3);
    CVssFunctionTracer::TranslateGenericError(
      &v30,
      &v22,
      2147549183LL,
      L"Unexpected error: dwIndex out of scope %lu %lu",
      lpReserveda,
      lpType);
  }
  v14 = *((_DWORD *)this + 4);
  v15 = Type;
  if ( Type != v14 )
  {
    v22 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v23 = L"CVssRegistryValueIterator::GetCurrentValueContent";
    v24 = L"REGREGSC";
    v25 = 989;
    v26 = 11;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    LODWORD(lpType) = v14;
    LODWORD(lpReserveda) = v15;
    CVssFunctionTracer::TranslateGenericError(
      &v30,
      &v22,
      2147549183LL,
      L"Unexpected error: current value type changed in the meantime %lu %lu",
      lpReserveda,
      lpType);
  }
  *a2 = Data;
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v30);
}

```

## disassembly

```asm
0x14000bc1c  mov     [rsp-8+arg_8], rbx
0x14000bc21  push    rbp
0x14000bc22  push    rsi
0x14000bc23  push    rdi
0x14000bc24  push    r12
0x14000bc26  push    r13
0x14000bc28  push    r14
0x14000bc2a  push    r15
0x14000bc2c  lea     rbp, [rsp-80h]
0x14000bc31  sub     rsp, 180h
0x14000bc38  mov     rsi, rdx
0x14000bc3b  mov     rbx, rcx
0x14000bc3e  lea     r15, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14000bc45  mov     [rsp+1B0h+var_150], r15
0x14000bc4a  lea     rax, aCvssregistryva_4; "CVssRegistryValueIterator::GetCurrentVa"...
0x14000bc51  mov     [rsp+1B0h+var_148], rax
0x14000bc56  lea     rax, aRegregsc; "REGREGSC"
0x14000bc5d  mov     [rsp+1B0h+var_140], rax
0x14000bc62  mov     [rsp+1B0h+var_138], 3BBh
0x14000bc6a  mov     [rsp+1B0h+var_134], 0Bh
0x14000bc72  mov     r13d, 0FFh
0x14000bc78  mov     [rbp+0B0h+var_130], r13d
0x14000bc7c  xor     r12d, r12d
0x14000bc7f  mov     [rbp+0B0h+var_B0], 1000000h
0x14000bc86  xor     edx, edx; Val
0x14000bc88  lea     r8d, [r12+78h]; Size
0x14000bc8d  lea     rcx, [rbp+0B0h+var_128]; void *
0x14000bc91  call    memset_0
0x14000bc96  mov     [rbp+0B0h+var_98], r12d
0x14000bc9a  mov     rax, [rsp+1B0h+var_148]
0x14000bc9f  mov     [rbp+0B0h+var_78], rax
0x14000bca3  mov     rax, [rsp+1B0h+var_150]
0x14000bca8  mov     [rbp+0B0h+var_90], rax
0x14000bcac  mov     rax, [rsp+1B0h+var_140]
0x14000bcb1  mov     [rbp+0B0h+var_88], rax
0x14000bcb5  mov     eax, [rsp+1B0h+var_138]
0x14000bcb9  mov     [rbp+0B0h+var_80], eax
0x14000bcbc  mov     eax, [rsp+1B0h+var_134]
0x14000bcc0  mov     [rbp+0B0h+var_7C], eax
0x14000bcc3  call    cs:__imp_GetTickCount
0x14000bcc9  mov     [rbp+0B0h+var_6C], eax
0x14000bccc  mov     [rbp+0B0h+var_9C], 0FFFFFFFFh
0x14000bcd3  mov     eax, [rbp+0B0h+var_130]
0x14000bcd6  mov     [rbp+0B0h+var_68], eax
0x14000bcd9  mov     [rbp+0B0h+var_A0], r12d
0x14000bcdd  mov     [rbp+0B0h+var_40], r12
0x14000bce1  xorps   xmm0, xmm0
0x14000bce4  movups  [rbp+0B0h+var_60], xmm0
0x14000bce8  movups  [rbp+0B0h+var_50], xmm0
0x14000bcec  mov     [rsp+1B0h+var_160], r12
0x14000bcf1  lea     rcx, [rsp+1B0h+var_160]
0x14000bcf6  call    cs:__imp_VssGetTracingContextPerThread
0x14000bcfc  test    eax, eax
0x14000bcfe  js      short loc_14000BD1C
0x14000bd00  lea     rcx, [rbp+0B0h+var_A0]
0x14000bd04  call    cs:__imp_VssSetTracingContextPerThread
0x14000bd0a  mov     rcx, [rbp+0B0h+var_40]
0x14000bd0e  test    eax, eax
0x14000bd10  cmovns  rcx, [rsp+1B0h+var_160]
0x14000bd16  mov     [rbp+0B0h+var_40], rcx
0x14000bd1a  jmp     short loc_14000BD20
0x14000bd1c  mov     rcx, [rbp+0B0h+var_40]
0x14000bd20  test    rcx, rcx
0x14000bd23  jz      short loc_14000BD2F
0x14000bd25  mov     eax, [rcx+30h]
0x14000bd28  inc     eax
0x14000bd2a  mov     [rbp+0B0h+var_70], eax
0x14000bd2d  jmp     short loc_14000BD33
0x14000bd2f  mov     [rbp+0B0h+var_70], r12d
0x14000bd33  mov     edi, 0A0h
0x14000bd38  cmp     [rbp+0B0h+var_68], r13d
0x14000bd3c  cmovnz  edi, [rbp+0B0h+var_68]
0x14000bd40  lea     rcx, [rbp+0B0h+var_A0]; this
0x14000bd44  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14000bd49  test    eax, eax
0x14000bd4b  jz      short loc_14000BD88
0x14000bd4d  mov     [rsp+1B0h+var_170], r12
0x14000bd52  mov     dword ptr [rsp+1B0h+lpcbData], edi
0x14000bd56  lea     rax, aEnter; "ENTER"
0x14000bd5d  mov     [rsp+1B0h+lpData], rax
0x14000bd62  mov     rax, [rbp+0B0h+var_78]
0x14000bd66  mov     [rsp+1B0h+lpType], rax
0x14000bd6b  mov     eax, [rbp+0B0h+var_7C]
0x14000bd6e  mov     dword ptr [rsp+1B0h+lpReserved], eax
0x14000bd72  mov     r9d, [rbp+0B0h+var_70]
0x14000bd76  mov     r8d, [rbp+0B0h+var_80]
0x14000bd7a  mov     rdx, [rbp+0B0h+var_88]
0x14000bd7e  mov     rcx, [rbp+0B0h+var_90]
0x14000bd82  call    cs:__imp_VssTraceMessage
0x14000bd88  lea     rcx, [rsp+1B0h+var_150]; this
0x14000bd8d  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14000bd92  nop
0x14000bd93  mov     rcx, rbx; this
0x14000bd96  call    ?ReadCurrentValueDetails@CVssRegistryValueIterator@@AEAAXXZ; CVssRegistryValueIterator::ReadCurrentValueDetails(void)
0x14000bd9b  mov     r14d, 4
0x14000bda1  cmp     [rbx+10h], r14d
0x14000bda5  jz      short loc_14000BE0A
0x14000bda7  mov     [rsp+1B0h+var_150], r15
0x14000bdac  lea     rax, aCvssregistryva_4; "CVssRegistryValueIterator::GetCurrentVa"...
0x14000bdb3  mov     [rsp+1B0h+var_148], rax
0x14000bdb8  lea     rax, aRegregsc; "REGREGSC"
0x14000bdbf  mov     [rsp+1B0h+var_140], rax
0x14000bdc4  mov     [rsp+1B0h+var_138], 3C1h
0x14000bdcc  mov     [rsp+1B0h+var_134], 0Bh
0x14000bdd4  mov     [rbp+0B0h+var_130], r13d
0x14000bdd8  mov     [rbp+0B0h+var_B0], 1000000h
0x14000bddf  xor     edx, edx; Val
0x14000bde1  lea     r8d, [r14+74h]; Size
0x14000bde5  lea     rcx, [rbp+0B0h+var_128]; void *
0x14000bde9  call    memset_0
0x14000bdee  lea     r9, aUnexpectedErro_6; "Unexpected error: attempting to read a "...
0x14000bdf5  mov     r8d, 8000FFFFh
0x14000bdfb  lea     rdx, [rsp+1B0h+var_150]
0x14000be00  lea     rcx, [rbp+0B0h+var_A0]
0x14000be04  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14000be0a  mov     edi, [rbx+2Ch]
0x14000be0d  cmp     edi, r14d
0x14000be10  jz      short loc_14000BE7E
0x14000be12  mov     [rsp+1B0h+var_150], r15
0x14000be17  lea     rax, aCvssregistryva_4; "CVssRegistryValueIterator::GetCurrentVa"...
0x14000be1e  mov     [rsp+1B0h+var_148], rax
0x14000be23  lea     rax, aRegregsc; "REGREGSC"
0x14000be2a  mov     [rsp+1B0h+var_140], rax
0x14000be2f  mov     [rsp+1B0h+var_138], 3C6h
0x14000be37  mov     [rsp+1B0h+var_134], 0Bh
0x14000be3f  mov     [rbp+0B0h+var_130], r13d
0x14000be43  mov     [rbp+0B0h+var_B0], 1000000h
0x14000be4a  xor     edx, edx; Val
0x14000be4c  lea     r8d, [rdx+78h]; Size
0x14000be50  lea     rcx, [rbp+0B0h+var_128]; void *
0x14000be54  call    memset_0
0x14000be59  mov     [rsp+1B0h+lpType], r14
0x14000be5e  mov     dword ptr [rsp+1B0h+lpReserved], edi
0x14000be62  lea     r9, aUnexpectedErro_0; "Unexpected error: unexpected DWORD size"...
0x14000be69  mov     r8d, 8000FFFFh
0x14000be6f  lea     rdx, [rsp+1B0h+var_150]
0x14000be74  lea     rcx, [rbp+0B0h+var_A0]
0x14000be78  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14000be7e  mov     [rbp+0B0h+Data], r12d
0x14000be85  mov     eax, [rbx+28h]
0x14000be88  mov     [rbp+0B0h+cchValueName], eax
0x14000be8e  mov     [rbp+0B0h+Type], r12d
0x14000be95  mov     [rsp+1B0h+cbData], r14d
0x14000be9a  lea     rax, [rsp+1B0h+cbData]
0x14000be9f  mov     [rsp+1B0h+lpcbData], rax; lpcbData
0x14000bea4  lea     rax, [rbp+0B0h+Data]
0x14000beab  mov     [rsp+1B0h+lpData], rax; lpData
0x14000beb0  lea     rax, [rbp+0B0h+Type]
0x14000beb7  mov     [rsp+1B0h+lpType], rax; lpType
0x14000bebc  mov     [rsp+1B0h+lpReserved], r12; lpReserved
0x14000bec1  lea     r9, [rbp+0B0h+cchValueName]; lpcchValueName
0x14000bec8  mov     r8, [rbx+20h]; lpValueName
0x14000becc  mov     edx, [rbx+0Ch]; dwIndex
0x14000becf  mov     rcx, [rbx]; hKey
0x14000bed2  call    cs:__imp_RegEnumValueW
0x14000bed8  mov     edi, eax
0x14000beda  test    eax, eax
0x14000bedc  jz      loc_14000BFF6
0x14000bee2  cmp     eax, 103h
0x14000bee7  jz      loc_14000BF85
0x14000beed  mov     esi, [rbp+0B0h+cchValueName]
0x14000bef3  mov     r14, [rbx+20h]
0x14000bef7  mov     r15d, [rbx+0Ch]
0x14000befb  mov     rbx, [rbx]
0x14000befe  test    eax, eax
0x14000bf00  jle     short loc_14000BF0B
0x14000bf02  movzx   edi, ax
0x14000bf05  or      edi, 80070000h
0x14000bf0b  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14000bf12  mov     [rsp+1B0h+var_150], rax
0x14000bf17  lea     rax, aCvssregistryva_4; "CVssRegistryValueIterator::GetCurrentVa"...
0x14000bf1e  mov     [rsp+1B0h+var_148], rax
0x14000bf23  lea     rax, aRegregsc; "REGREGSC"
0x14000bf2a  mov     [rsp+1B0h+var_140], rax
0x14000bf2f  mov     [rsp+1B0h+var_138], 3E5h
0x14000bf37  mov     [rsp+1B0h+var_134], 0Bh
0x14000bf3f  mov     [rbp+0B0h+var_130], r13d
0x14000bf43  mov     [rbp+0B0h+var_B0], 1000000h
0x14000bf4a  xor     edx, edx; Val
0x14000bf4c  lea     r8d, [rdx+78h]; Size
0x14000bf50  lea     rcx, [rbp+0B0h+var_128]; void *
0x14000bf54  call    memset_0
0x14000bf59  mov     dword ptr [rsp+1B0h+lpcbData], esi
0x14000bf5d  mov     [rsp+1B0h+lpData], r14
0x14000bf62  mov     dword ptr [rsp+1B0h+lpType], r15d
0x14000bf67  mov     [rsp+1B0h+lpReserved], rbx
0x14000bf6c  lea     r9, aRegenumvaluePL; "RegEnumValue(%p,%lu,%p,%lu ...)"
0x14000bf73  mov     r8d, edi
0x14000bf76  lea     rdx, [rsp+1B0h+var_150]
0x14000bf7b  lea     rcx, [rbp+0B0h+var_A0]
0x14000bf7f  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14000bf85  mov     [rsp+1B0h+var_150], r15
0x14000bf8a  lea     rax, aCvssregistryva_4; "CVssRegistryValueIterator::GetCurrentVa"...
0x14000bf91  mov     [rsp+1B0h+var_148], rax
0x14000bf96  lea     rax, aRegregsc; "REGREGSC"
0x14000bf9d  mov     [rsp+1B0h+var_140], rax
0x14000bfa2  mov     [rsp+1B0h+var_138], 3E3h
0x14000bfaa  mov     [rsp+1B0h+var_134], 0Bh
0x14000bfb2  mov     [rbp+0B0h+var_130], r13d
0x14000bfb6  mov     [rbp+0B0h+var_B0], 1000000h
0x14000bfbd  xor     edx, edx; Val
0x14000bfbf  lea     r8d, [rdx+78h]; Size
0x14000bfc3  lea     rcx, [rbp+0B0h+var_128]; void *
0x14000bfc7  call    memset_0
0x14000bfcc  mov     eax, [rbx+8]
0x14000bfcf  mov     dword ptr [rsp+1B0h+lpType], eax
0x14000bfd3  mov     eax, [rbx+0Ch]
0x14000bfd6  mov     dword ptr [rsp+1B0h+lpReserved], eax
0x14000bfda  lea     r9, aUnexpectedErro_11; "Unexpected error: dwIndex out of scope "...
0x14000bfe1  mov     r8d, 8000FFFFh
0x14000bfe7  lea     rdx, [rsp+1B0h+var_150]
0x14000bfec  lea     rcx, [rbp+0B0h+var_A0]
0x14000bff0  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14000bff6  mov     ebx, [rbx+10h]
0x14000bff9  mov     edi, [rbp+0B0h+Type]
0x14000bfff  cmp     edi, ebx
0x14000c001  jz      short loc_14000C06E
0x14000c003  mov     [rsp+1B0h+var_150], r15
0x14000c008  lea     rax, aCvssregistryva_4; "CVssRegistryValueIterator::GetCurrentVa"...
0x14000c00f  mov     [rsp+1B0h+var_148], rax
0x14000c014  lea     rax, aRegregsc; "REGREGSC"
0x14000c01b  mov     [rsp+1B0h+var_140], rax
0x14000c020  mov     [rsp+1B0h+var_138], 3DDh
0x14000c028  mov     [rsp+1B0h+var_134], 0Bh
0x14000c030  mov     [rbp+0B0h+var_130], r13d
0x14000c034  mov     [rbp+0B0h+var_B0], 1000000h
0x14000c03b  xor     edx, edx; Val
0x14000c03d  lea     r8d, [rdx+78h]; Size
0x14000c041  lea     rcx, [rbp+0B0h+var_128]; void *
0x14000c045  call    memset_0
0x14000c04a  mov     dword ptr [rsp+1B0h+lpType], ebx
0x14000c04e  mov     dword ptr [rsp+1B0h+lpReserved], edi
0x14000c052  lea     r9, aUnexpectedErro_2; "Unexpected error: current value type ch"...
0x14000c059  mov     r8d, 8000FFFFh
0x14000c05f  lea     rdx, [rsp+1B0h+var_150]
0x14000c064  lea     rcx, [rbp+0B0h+var_A0]
0x14000c068  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14000c06e  mov     eax, [rbp+0B0h+Data]
0x14000c074  mov     [rsi], eax
0x14000c076  lea     rcx, [rbp+0B0h+var_A0]; this
0x14000c07a  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14000c07f  mov     rbx, [rsp+1B0h+arg_8]
0x14000c087  add     rsp, 180h
0x14000c08e  pop     r15
0x14000c090  pop     r14
0x14000c092  pop     r13
0x14000c094  pop     r12
0x14000c096  pop     rdi
0x14000c097  pop     rsi
0x14000c098  pop     rbp
0x14000c099  retn
```
