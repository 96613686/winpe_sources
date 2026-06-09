# BaseSrvSxsDoSystemDefaultActivationContext

- ea: `0x180001450`
- end: `0x180001d5b`
- name: `BaseSrvSxsDoSystemDefaultActivationContext`
- size: `2315`
- prototype: `__int64 __fastcall(unsigned __int16, union _LARGE_INTEGER, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001d70`

## callees

- `0x180001350`
- `0x180001450`
- `0x180003310`
- `0x180006ccd`
- `0x180006cf0`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180001576`
- `ntdll!RtlEnterCriticalSection` at `0x180001ac3`
- `ntdll!RtlEnterCriticalSection` at `0x180001576`
- `ntdll!RtlEnterCriticalSection` at `0x180001ac3`
- `ntdll!RtlLeaveCriticalSection` at `0x180001611`
- `ntdll!RtlLeaveCriticalSection` at `0x180001704`
- `ntdll!RtlLeaveCriticalSection` at `0x180001c53`
- `ntdll!RtlLeaveCriticalSection` at `0x180006dba`
- `ntdll!RtlLeaveCriticalSection` at `0x180001611`
- `ntdll!RtlLeaveCriticalSection` at `0x180001704`
- `ntdll!RtlLeaveCriticalSection` at `0x180001c53`
- `ntdll!RtlLeaveCriticalSection` at `0x180006dba`
- `ntdll!NtClose` at `0x180001af8`
- `ntdll!NtClose` at `0x180001af8`
- `ntdll!DbgPrintEx` at `0x180006f5e`
- `ntdll!DbgPrintEx` at `0x180006f5e`
- `ntdll!NtWriteVirtualMemory` at `0x18000165f`
- `ntdll!NtWriteVirtualMemory` at `0x1800016c4`
- `ntdll!NtWriteVirtualMemory` at `0x18000165f`
- `ntdll!NtWriteVirtualMemory` at `0x1800016c4`
- `ntdll!NtUnmapViewOfSection` at `0x180001c3e`
- `ntdll!NtUnmapViewOfSection` at `0x180006f7b`
- `ntdll!NtUnmapViewOfSection` at `0x180001c3e`
- `ntdll!NtUnmapViewOfSection` at `0x180006f7b`
- `ntdll!RtlpApplyLengthFunction` at `0x180001811`
- `ntdll!RtlpApplyLengthFunction` at `0x180001811`
- `ntdll!RtlGetLengthWithoutTrailingPathSeperators` at `0x1800017fb`
- `ntdll!RtlFreeUnicodeString` at `0x180001c85`
- `ntdll!RtlFreeUnicodeString` at `0x180001cdc`
- `ntdll!RtlFreeUnicodeString` at `0x180001d20`
- `ntdll!RtlFreeUnicodeString` at `0x180006dfa`
- `ntdll!RtlFreeUnicodeString` at `0x180006e7a`
- `ntdll!RtlFreeUnicodeString` at `0x180006efa`
- `ntdll!RtlFreeUnicodeString` at `0x180001c85`
- `ntdll!RtlFreeUnicodeString` at `0x180001cdc`
- `ntdll!RtlFreeUnicodeString` at `0x180001d20`
- `ntdll!RtlFreeUnicodeString` at `0x180006dfa`
- `ntdll!RtlFreeUnicodeString` at `0x180006e7a`
- `ntdll!RtlFreeUnicodeString` at `0x180006efa`
- `ntdll!RtlMultiAppendUnicodeStringBuffer` at `0x180001880`
- `ntdll!RtlMultiAppendUnicodeStringBuffer` at `0x180001975`
- `ntdll!RtlMultiAppendUnicodeStringBuffer` at `0x180001880`
- `ntdll!RtlMultiAppendUnicodeStringBuffer` at `0x180001975`
- `ntdll!NtMapViewOfSection` at `0x1800015f4`
- `ntdll!NtMapViewOfSection` at `0x1800015f4`

## string_xrefs

- `0x18000190c`: `Microsoft.Windows.SystemCompatible,version="6.0.0.0",type="win32",publicKeyToken="6595b64144ccf1df",processorArchitecture="`

## pseudocode

```c
__int64 __fastcall BaseSrvSxsDoSystemDefaultActivationContext(
        unsigned __int16 a1,
        union _LARGE_INTEGER a2,
        __int64 a3,
        __int64 a4)
{
  void *QuadPart; // r13
  int v5; // ebx
  __int64 *v6; // r15
  unsigned int i; // edx
  __int64 v8; // rax
  void *v9; // rcx
  int LanguageFallbacks; // edi
  SIZE_T v11; // r9
  SIZE_T v12; // r14
  unsigned int Length; // r13d
  UCHAR *StaticBuffer; // rcx
  _WORD *v15; // rcx
  _WORD *v16; // rcx
  PVOID BaseAddress; // [rsp+58h] [rbp-650h] BYREF
  union _LARGE_INTEGER SectionOffset; // [rsp+60h] [rbp-648h] BYREF
  unsigned int v20; // [rsp+68h] [rbp-640h]
  HANDLE Handle; // [rsp+70h] [rbp-638h] BYREF
  ULONG_PTR ViewSize; // [rsp+78h] [rbp-630h] BYREF
  struct _UNICODE_STRING UnicodeStringOrUnicodeStringBuffer; // [rsp+80h] [rbp-628h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+90h] [rbp-618h] BYREF
  struct _UNICODE_STRING v25; // [rsp+A0h] [rbp-608h] BYREF
  struct _UNICODE_STRING v26; // [rsp+B0h] [rbp-5F8h] BYREF
  __int64 v27; // [rsp+C0h] [rbp-5E8h]
  __int64 v28; // [rsp+C8h] [rbp-5E0h]
  union _LARGE_INTEGER v29; // [rsp+D0h] [rbp-5D8h]
  UNICODE_STRING Addends; // [rsp+D8h] [rbp-5D0h] BYREF
  int v31; // [rsp+E8h] [rbp-5C0h]
  const wchar_t *v32; // [rsp+F0h] [rbp-5B8h]
  __int64 v33; // [rsp+F8h] [rbp-5B0h]
  __int64 v34; // [rsp+100h] [rbp-5A8h]
  __int64 v35; // [rsp+108h] [rbp-5A0h]
  __int64 v36; // [rsp+110h] [rbp-598h]
  _RTL_UNICODE_STRING_BUFFER StringBuffer; // [rsp+118h] [rbp-590h] BYREF
  __int128 v38; // [rsp+160h] [rbp-548h]
  __int128 v39; // [rsp+170h] [rbp-538h]
  __int64 v40; // [rsp+180h] [rbp-528h]
  __int128 v41; // [rsp+188h] [rbp-520h] BYREF
  __int128 v42; // [rsp+198h] [rbp-510h]
  __int128 v43; // [rsp+1A8h] [rbp-500h]
  __int64 v44; // [rsp+1B8h] [rbp-4F0h]
  unsigned int v45; // [rsp+1C0h] [rbp-4E8h] BYREF
  __int16 v46; // [rsp+1C4h] [rbp-4E4h]
  __int128 v47; // [rsp+1C8h] [rbp-4E0h]
  char v48; // [rsp+1D9h] [rbp-4CFh]
  int v49; // [rsp+1E0h] [rbp-4C8h]
  int v50; // [rsp+1E4h] [rbp-4C4h]
  const wchar_t *v51; // [rsp+1E8h] [rbp-4C0h]
  __int16 v52; // [rsp+248h] [rbp-460h]
  USHORT MaximumLength; // [rsp+24Ah] [rbp-45Eh]
  int v54; // [rsp+24Ch] [rbp-45Ch]
  PWSTR Buffer; // [rsp+250h] [rbp-458h]
  PVOID ReservedForIMalloc; // [rsp+258h] [rbp-450h]
  __int64 v57; // [rsp+260h] [rbp-448h]
  UNICODE_STRING v58; // [rsp+3C0h] [rbp-2E8h] BYREF
  __int16 v59; // [rsp+3D0h] [rbp-2D8h]
  __int16 v60; // [rsp+3D2h] [rbp-2D6h]
  __int64 v61; // [rsp+3D8h] [rbp-2D0h]
  int v62; // [rsp+3E0h] [rbp-2C8h]
  const wchar_t *v63; // [rsp+3E8h] [rbp-2C0h]
  _WORD v64[24]; // [rsp+3F0h] [rbp-2B8h] BYREF
  _WORD v65[128]; // [rsp+420h] [rbp-288h] BYREF
  _WORD v66[160]; // [rsp+520h] [rbp-188h] BYREF

  v28 = a4;
  v27 = a3;
  QuadPart = (void *)a2.QuadPart;
  SectionOffset = a2;
  v5 = a1;
  v29 = a2;
  Handle = 0;
  v6 = 0;
  memset_0(&v45, 0, 0x1F8u);
  memset(&StringBuffer, 0, sizeof(StringBuffer));
  UnicodeStringOrUnicodeStringBuffer = 0;
  ViewSize = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  BaseAddress = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v20 = 0;
  for ( i = 0; ; ++i )
  {
    v20 = i;
    if ( i == 5 )
      break;
    v8 = 4LL * i;
    if ( LODWORD(SxsSystemDefaultActivationContexts[v8 + 3]) == v5 )
    {
      v6 = &SxsSystemDefaultActivationContexts[v8];
      break;
    }
  }
  if ( !v6 )
  {
    LanguageFallbacks = -1073741823;
    goto LABEL_32;
  }
  RtlEnterCriticalSection(&BaseSrvSxsSystemDefaultActivationContextCriticalSection);
  if ( !*v6 )
  {
    RtlLeaveCriticalSection(&BaseSrvSxsSystemDefaultActivationContextCriticalSection);
    v33 = 256;
    *(_QWORD *)&v42 = v65;
    *(_QWORD *)&v43 = 256;
    *((_QWORD *)&v42 + 1) = v65;
    *((_QWORD *)&v43 + 1) = 256;
    *((_QWORD *)&v41 + 1) = v65;
    v65[0] = 0;
    LODWORD(v41) = 0x1000000;
    LanguageFallbacks = BasepSxsGetLanguageFallbacks(256, &v41);
    if ( LanguageFallbacks < 0 )
      goto LABEL_32;
    v34 = 46;
    StringBuffer.ByteBuffer.Buffer = (PUCHAR)v64;
    StringBuffer.ByteBuffer.Size = 46;
    StringBuffer.ByteBuffer.StaticBuffer = (PUCHAR)v64;
    StringBuffer.ByteBuffer.StaticSize = 46;
    StringBuffer.String.Buffer = v64;
    v64[0] = 0;
    *(_DWORD *)&StringBuffer.String.Length = 3014656;
    UnicodeStringOrUnicodeStringBuffer = BaseSrvWindowsDirectory;
    RtlpApplyLengthFunction(0, 0x10u, &UnicodeStringOrUnicodeStringBuffer, RtlGetLengthWithoutTrailingPathSeperators);
    *(_DWORD *)&Addends.Length = *(_DWORD *)&UnicodeStringOrUnicodeStringBuffer.Length;
    Addends.Buffer = UnicodeStringOrUnicodeStringBuffer.Buffer;
    v31 = 1048590;
    v32 = L"\\WinSxs";
    LanguageFallbacks = RtlMultiAppendUnicodeStringBuffer(&StringBuffer, 2u, &Addends);
    if ( LanguageFallbacks < 0 )
      goto LABEL_32;
    Length = StringBuffer.String.Length;
    v35 = 318;
    *(_QWORD *)&v38 = v66;
    *(_QWORD *)&v39 = 318;
    *((_QWORD *)&v38 + 1) = v66;
    *((_QWORD *)&v39 + 1) = 318;
    *(_QWORD *)&StringBuffer.MinimumStaticBufferForTerminalNul = v66;
    v66[0] = 0;
    LODWORD(StringBuffer.ByteBuffer.ReservedForIMalloc) = 20840448;
    *(_DWORD *)&v58.Length = 16253174;
    v58.Buffer = L"Microsoft.Windows.SystemCompatible,version=\"6.0.0.0\",type=\"win32\",publicKeyToken=\"6595b64144ccf1df"
                  "\",processorArchitecture=\"";
    v59 = *((_WORD *)v6 + 4);
    v60 = *((_WORD *)v6 + 5);
    v61 = v6[2];
    v62 = 262146;
    v63 = L"\"";
    LanguageFallbacks = RtlMultiAppendUnicodeStringBuffer(
                          (PRTL_UNICODE_STRING_BUFFER)&StringBuffer.ByteBuffer.ReservedForIMalloc,
                          3u,
                          &v58);
    if ( LanguageFallbacks < 0 )
      goto LABEL_31;
    v45 = 12;
    ReservedForIMalloc = StringBuffer.ByteBuffer.ReservedForIMalloc;
    v57 = *(_QWORD *)&StringBuffer.MinimumStaticBufferForTerminalNul;
    MaximumLength = StringBuffer.String.MaximumLength;
    v54 = *(_DWORD *)(&StringBuffer.String.MaximumLength + 1);
    Buffer = StringBuffer.String.Buffer;
    v52 = Length;
    StringBuffer.String.Buffer[(unsigned __int64)Length >> 1] = 0;
    v48 = 1;
    v49 = 3014700;
    v50 = ViewSize;
    v51 = L"System Default Context";
    v47 = v41;
    v46 = v5;
    LanguageFallbacks = BaseSrvSxsCreateActivationContextFromStructEx(
                          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                          (void *)0xFFFFFFFFFFFFFFFFLL,
                          &v45,
                          0,
                          &Handle);
    if ( LanguageFallbacks < 0 )
    {
LABEL_31:
      QuadPart = (void *)SectionOffset.QuadPart;
      goto LABEL_32;
    }
    RtlEnterCriticalSection(&BaseSrvSxsSystemDefaultActivationContextCriticalSection);
    if ( *v6 )
      NtClose(Handle);
    else
      *v6 = (__int64)Handle;
    Handle = 0;
    QuadPart = (void *)SectionOffset.QuadPart;
  }
  ViewSize = 0;
  v36 = 0;
  v9 = (void *)*v6;
  BaseAddress = 0;
  SectionOffset.QuadPart = 0;
  LanguageFallbacks = NtMapViewOfSection(
                        v9,
                        QuadPart,
                        &BaseAddress,
                        0,
                        0,
                        &SectionOffset,
                        &ViewSize,
                        ViewShare,
                        0x400000u,
                        2u);
  RtlLeaveCriticalSection(&BaseSrvSxsSystemDefaultActivationContextCriticalSection);
  if ( LanguageFallbacks >= 0 )
  {
    if ( v5 == 10 || v5 == 13 )
    {
      v11 = 4;
      v12 = 8;
    }
    else
    {
      v12 = 8;
      v11 = 8;
    }
    LanguageFallbacks = NtWriteVirtualMemory(QuadPart, (PVOID)(v27 + 776), &BaseAddress, v11, 0);
    if ( LanguageFallbacks >= 0 )
    {
      if ( !v28 )
        goto LABEL_13;
      if ( v5 == 10 || v5 == 13 )
        v12 = 4;
      LanguageFallbacks = NtWriteVirtualMemory(QuadPart, (PVOID)(v28 + 512), &BaseAddress, v12, 0);
      if ( LanguageFallbacks >= 0 )
      {
LABEL_13:
        LanguageFallbacks = 0;
        BaseAddress = 0;
      }
    }
  }
LABEL_32:
  StaticBuffer = StringBuffer.ByteBuffer.StaticBuffer;
  if ( StringBuffer.ByteBuffer.Buffer )
  {
    if ( StringBuffer.ByteBuffer.Buffer != StringBuffer.ByteBuffer.StaticBuffer )
    {
      *(_QWORD *)&UnicodeString.Length = 0;
      UnicodeString.Buffer = (PWSTR)StringBuffer.ByteBuffer.Buffer;
      RtlFreeUnicodeString(&UnicodeString);
      StaticBuffer = StringBuffer.ByteBuffer.StaticBuffer;
    }
    StringBuffer.ByteBuffer.Buffer = StaticBuffer;
    StringBuffer.ByteBuffer.Size = StringBuffer.ByteBuffer.StaticSize;
  }
  StringBuffer.String.Buffer = (PWSTR)StaticBuffer;
  if ( StaticBuffer )
    *(_WORD *)StaticBuffer = 0;
  StringBuffer.String.Length = 0;
  StringBuffer.String.MaximumLength = StringBuffer.ByteBuffer.StaticSize;
  v15 = (_WORD *)*((_QWORD *)&v38 + 1);
  if ( (_QWORD)v38 )
  {
    if ( (_QWORD)v38 != *((_QWORD *)&v38 + 1) )
    {
      *(_QWORD *)&v25.Length = 0;
      v25.Buffer = (PWSTR)v38;
      RtlFreeUnicodeString(&v25);
      v15 = (_WORD *)*((_QWORD *)&v38 + 1);
    }
    *(_QWORD *)&v38 = v15;
    *(_QWORD *)&v39 = *((_QWORD *)&v39 + 1);
  }
  *(_QWORD *)&StringBuffer.MinimumStaticBufferForTerminalNul = v15;
  if ( v15 )
    *v15 = 0;
  LOWORD(StringBuffer.ByteBuffer.ReservedForIMalloc) = 0;
  WORD1(StringBuffer.ByteBuffer.ReservedForIMalloc) = WORD4(v39);
  v16 = (_WORD *)*((_QWORD *)&v42 + 1);
  if ( (_QWORD)v42 )
  {
    if ( (_QWORD)v42 != *((_QWORD *)&v42 + 1) )
    {
      *(_QWORD *)&v26.Length = 0;
      v26.Buffer = (PWSTR)v42;
      RtlFreeUnicodeString(&v26);
      v16 = (_WORD *)*((_QWORD *)&v42 + 1);
    }
    *(_QWORD *)&v42 = v16;
    *(_QWORD *)&v43 = *((_QWORD *)&v43 + 1);
  }
  *((_QWORD *)&v41 + 1) = v16;
  if ( v16 )
    *v16 = 0;
  LOWORD(v41) = 0;
  WORD1(v41) = WORD4(v43);
  if ( BaseAddress )
    NtUnmapViewOfSection(QuadPart, BaseAddress);
  return (unsigned int)LanguageFallbacks;
}

```

## disassembly

```asm
0x180001450  push    rbx
0x180001452  push    rsi
0x180001453  push    rdi
0x180001454  push    r12
0x180001456  push    r13
0x180001458  push    r14
0x18000145a  push    r15
0x18000145c  sub     rsp, 670h
0x180001463  mov     rax, cs:__security_cookie
0x18000146a  xor     rax, rsp
0x18000146d  mov     [rsp+6A8h+var_48], rax
0x180001475  mov     [rsp+6A8h+var_5E0], r9
0x18000147d  mov     [rsp+6A8h+var_5E8], r8
0x180001485  mov     r13, rdx
0x180001488  mov     qword ptr [rsp+6A8h+var_648], rdx
0x18000148d  movzx   ebx, cx
0x180001490  mov     [rsp+6A8h+var_5D8], rdx
0x180001498  xor     edi, edi
0x18000149a  mov     [rsp+6A8h+Handle], rdi
0x18000149f  mov     r15d, edi
0x1800014a2  xor     edx, edx; Val
0x1800014a4  mov     r8d, 1F8h; Size
0x1800014aa  lea     rcx, [rsp+6A8h+var_4E8]; void *
0x1800014b2  call    memset_0
0x1800014b7  xorps   xmm0, xmm0
0x1800014ba  xor     eax, eax
0x1800014bc  movups  xmmword ptr [rsp+6A8h+StringBuffer.String.Length], xmm0
0x1800014c4  movups  xmmword ptr [rsp+6A8h+StringBuffer.ByteBuffer.Buffer], xmm0
0x1800014cc  movups  xmmword ptr [rsp+6A8h+StringBuffer.ByteBuffer.Size], xmm0
0x1800014d4  mov     [rsp+6A8h+StringBuffer.ByteBuffer.ReservedForAllocatedSize], rax
0x1800014dc  movups  [rsp+6A8h+UnicodeStringOrUnicodeStringBuffer], xmm0
0x1800014e4  mov     esi, 2Eh ; '.'
0x1800014e9  mov     [rsp+6A8h+var_630], rax
0x1800014ee  movups  xmmword ptr [rsp+6A8h+StringBuffer.ByteBuffer.ReservedForIMalloc], xmm0
0x1800014f6  movups  [rsp+6A8h+var_548], xmm0
0x1800014fe  movups  [rsp+6A8h+var_538], xmm0
0x180001506  mov     [rsp+6A8h+var_528], rax
0x18000150e  mov     [rsp+6A8h+BaseAddress], rdi
0x180001513  xor     r12b, r12b
0x180001516  mov     [rsp+6A8h+var_658], r12b
0x18000151b  movups  [rsp+6A8h+var_520], xmm0
0x180001523  movups  [rsp+6A8h+var_510], xmm0
0x18000152b  movups  [rsp+6A8h+var_500], xmm0
0x180001533  mov     [rsp+6A8h+var_4F0], rax
0x18000153b  mov     [rsp+6A8h+var_640], edi
0x18000153f  mov     edx, edi
0x180001541  lea     r8, SxsSystemDefaultActivationContexts
0x180001548  mov     [rsp+6A8h+var_640], edx
0x18000154c  cmp     edx, 5
0x18000154f  jz      short loc_180001566
0x180001551  mov     eax, edx
0x180001553  shl     rax, 5
0x180001557  cmp     [rax+r8+18h], ebx
0x18000155c  jz      short loc_180001562
0x18000155e  inc     edx
0x180001560  jmp     short loc_180001548
0x180001562  lea     r15, [rax+r8]
0x180001566  test    r15, r15
0x180001569  jz      loc_1800016F3
0x18000156f  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection; CriticalSection
0x180001576  call    cs:__imp_RtlEnterCriticalSection
0x18000157d  nop     dword ptr [rax+rax+00h]
0x180001582  mov     [rsp+6A8h+var_658], 1
0x180001587  cmp     qword ptr [r15], 0
0x18000158b  jz      loc_1800016FD
0x180001591  mov     esi, 4
0x180001596  mov     r14d, 2
0x18000159c  mov     [rsp+6A8h+var_630], rdi
0x1800015a1  mov     [rsp+6A8h+var_598], rdi
0x1800015a9  mov     rcx, [r15]; SectionHandle
0x1800015ac  mov     qword ptr [rsp+6A8h+var_648], rdi
0x1800015b1  mov     [rsp+6A8h+BaseAddress], rdi
0x1800015b6  mov     qword ptr [rsp+6A8h+var_648], rdi
0x1800015bb  mov     [rsp+6A8h+AccessProtection], r14d; AccessProtection
0x1800015c0  mov     [rsp+6A8h+AllocationType], 400000h; AllocationType
0x1800015c8  mov     [rsp+6A8h+InheritDisposition], 1; InheritDisposition
0x1800015d0  lea     rax, [rsp+6A8h+var_630]
0x1800015d5  mov     [rsp+6A8h+ViewSize], rax; ViewSize
0x1800015da  lea     rax, [rsp+6A8h+var_648]
0x1800015df  mov     [rsp+6A8h+SectionOffset], rax; SectionOffset
0x1800015e4  mov     [rsp+6A8h+CommitSize], rdi; CommitSize
0x1800015e9  xor     r9d, r9d; ZeroBits
0x1800015ec  lea     r8, [rsp+6A8h+BaseAddress]; BaseAddress
0x1800015f1  mov     rdx, r13; ProcessHandle
0x1800015f4  call    cs:__imp_NtMapViewOfSection
0x1800015fb  nop     dword ptr [rax+rax+00h]
0x180001600  mov     edi, eax
0x180001602  test    eax, eax
0x180001604  jns     loc_18000168E
0x18000160a  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection; CriticalSection
0x180001611  call    cs:__imp_RtlLeaveCriticalSection
0x180001618  nop     dword ptr [rax+rax+00h]
0x18000161d  xor     r12b, r12b
0x180001620  mov     [rsp+6A8h+var_658], r12b
0x180001625  test    edi, edi
0x180001627  js      loc_180001B19
0x18000162d  cmp     ebx, 0Ah
0x180001630  jnz     loc_1800016DC
0x180001636  mov     r9, rsi; NumberOfBytesToWrite
0x180001639  mov     r14d, 8
0x18000163f  mov     rdx, [rsp+6A8h+var_5E8]
0x180001647  add     rdx, 308h; BaseAddress
0x18000164e  mov     [rsp+6A8h+CommitSize], 0; NumberOfBytesWritten
0x180001657  lea     r8, [rsp+6A8h+BaseAddress]; Buffer
0x18000165c  mov     rcx, r13; ProcessHandle
0x18000165f  call    cs:__imp_NtWriteVirtualMemory
0x180001666  nop     dword ptr [rax+rax+00h]
0x18000166b  mov     edi, eax
0x18000166d  test    eax, eax
0x18000166f  js      loc_180001B19
0x180001675  mov     rdx, [rsp+6A8h+var_5E0]
0x18000167d  test    rdx, rdx
0x180001680  jnz     short loc_18000169D
0x180001682  xor     edi, edi
0x180001684  mov     [rsp+6A8h+BaseAddress], rdi
0x180001689  jmp     loc_180001B19
0x18000168e  mov     rax, [rsp+6A8h+BaseAddress]
0x180001693  mov     [rsp+6A8h+BaseAddress], rax
0x180001698  jmp     loc_18000160A
0x18000169d  cmp     ebx, 0Ah
0x1800016a0  jnz     loc_180001B06
0x1800016a6  mov     r14, rsi
0x1800016a9  add     rdx, 200h; BaseAddress
0x1800016b0  mov     [rsp+6A8h+CommitSize], 0; NumberOfBytesWritten
0x1800016b9  mov     r9, r14; NumberOfBytesToWrite
0x1800016bc  lea     r8, [rsp+6A8h+BaseAddress]; Buffer
0x1800016c1  mov     rcx, r13; ProcessHandle
0x1800016c4  call    cs:__imp_NtWriteVirtualMemory
0x1800016cb  nop     dword ptr [rax+rax+00h]
0x1800016d0  mov     edi, eax
0x1800016d2  test    eax, eax
0x1800016d4  js      loc_180001B19
0x1800016da  jmp     short loc_180001682
0x1800016dc  cmp     ebx, 0Dh
0x1800016df  jz      loc_180001636
0x1800016e5  mov     r14d, 8
0x1800016eb  mov     r9d, r14d
0x1800016ee  jmp     loc_18000163F
0x1800016f3  mov     edi, 0C0000001h
0x1800016f8  jmp     loc_180001B19
0x1800016fd  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection; CriticalSection
0x180001704  call    cs:__imp_RtlLeaveCriticalSection
0x18000170b  nop     dword ptr [rax+rax+00h]
0x180001710  xor     r12b, r12b
0x180001713  mov     [rsp+6A8h+var_658], r12b
0x180001718  mov     ecx, 100h
0x18000171d  mov     [rsp+6A8h+var_5B0], rcx
0x180001725  lea     rax, [rsp+6A8h+var_288]
0x18000172d  mov     qword ptr [rsp+6A8h+var_510], rax
0x180001735  mov     qword ptr [rsp+6A8h+var_500], rcx
0x18000173d  lea     rax, [rsp+6A8h+var_288]
0x180001745  mov     qword ptr [rsp+6A8h+var_510+8], rax
0x18000174d  mov     qword ptr [rsp+6A8h+var_500+8], rcx
0x180001755  lea     rax, [rsp+6A8h+var_288]
0x18000175d  mov     qword ptr [rsp+6A8h+var_520+8], rax
0x180001765  mov     [rsp+6A8h+var_288], di
0x18000176d  mov     dword ptr [rsp+6A8h+var_520], 1000000h
0x180001778  lea     rdx, [rsp+6A8h+var_520]
0x180001780  call    BasepSxsGetLanguageFallbacks
0x180001785  mov     edi, eax
0x180001787  test    eax, eax
0x180001789  js      loc_180001B19
0x18000178f  mov     [rsp+6A8h+var_5A8], rsi
0x180001797  lea     rax, [rsp+6A8h+var_2B8]
0x18000179f  mov     [rsp+6A8h+StringBuffer.ByteBuffer.Buffer], rax
0x1800017a7  mov     [rsp+6A8h+StringBuffer.ByteBuffer.Size], rsi
0x1800017af  lea     rax, [rsp+6A8h+var_2B8]
0x1800017b7  mov     [rsp+6A8h+StringBuffer.ByteBuffer.StaticBuffer], rax
0x1800017bf  mov     [rsp+6A8h+StringBuffer.ByteBuffer.StaticSize], rsi
0x1800017c7  lea     rax, [rsp+6A8h+var_2B8]
0x1800017cf  mov     [rsp+6A8h+StringBuffer.String.Buffer], rax
0x1800017d7  xor     eax, eax
0x1800017d9  mov     [rsp+6A8h+var_2B8], ax
0x1800017e1  mov     dword ptr [rsp+6A8h+StringBuffer.String.Length], 2E0000h
0x1800017ec  movups  xmm0, xmmword ptr cs:BaseSrvWindowsDirectory.Length
0x1800017f3  movups  [rsp+6A8h+UnicodeStringOrUnicodeStringBuffer], xmm0
0x1800017fb  mov     r9, cs:__imp_RtlGetLengthWithoutTrailingPathSeperators; LengthFunction
0x180001802  lea     r8, [rsp+6A8h+UnicodeStringOrUnicodeStringBuffer]; UnicodeStringOrUnicodeStringBuffer
0x18000180a  mov     edx, 10h; Type
0x18000180f  xor     ecx, ecx; Flags
0x180001811  call    cs:__imp_RtlpApplyLengthFunction
0x180001818  nop     dword ptr [rax+rax+00h]
0x18000181d  movzx   eax, word ptr [rsp+6A8h+UnicodeStringOrUnicodeStringBuffer]
0x180001825  mov     [rsp+6A8h+Addends.Length], ax
0x18000182d  movzx   eax, word ptr [rsp+6A8h+UnicodeStringOrUnicodeStringBuffer+2]
0x180001835  mov     [rsp+6A8h+Addends.MaximumLength], ax
0x18000183d  mov     rax, qword ptr [rsp+6A8h+UnicodeStringOrUnicodeStringBuffer+8]
0x180001845  mov     [rsp+6A8h+Addends.Buffer], rax
0x18000184d  mov     [rsp+6A8h+var_5C0], 10000Eh
0x180001858  lea     rax, aWinsxs; "\\WinSxs"
0x18000185f  mov     [rsp+6A8h+var_5B8], rax
0x180001867  lea     r8, [rsp+6A8h+Addends]; Addends
0x18000186f  mov     r14d, 2
0x180001875  mov     edx, r14d; NumberOfAddends
0x180001878  lea     rcx, [rsp+6A8h+StringBuffer]; StringBuffer
0x180001880  call    cs:__imp_RtlMultiAppendUnicodeStringBuffer
0x180001887  nop     dword ptr [rax+rax+00h]
0x18000188c  mov     edi, eax
0x18000188e  test    eax, eax
0x180001890  js      loc_180001B19
0x180001896  movzx   r13d, [rsp+6A8h+StringBuffer.String.Length]
0x18000189f  mov     ecx, 13Eh
0x1800018a4  mov     [rsp+6A8h+var_5A0], rcx
0x1800018ac  lea     rax, [rsp+6A8h+var_188]
0x1800018b4  mov     qword ptr [rsp+6A8h+var_548], rax
0x1800018bc  mov     qword ptr [rsp+6A8h+var_538], rcx
0x1800018c4  lea     rax, [rsp+6A8h+var_188]
0x1800018cc  mov     qword ptr [rsp+6A8h+var_548+8], rax
0x1800018d4  mov     qword ptr [rsp+6A8h+var_538+8], rcx
0x1800018dc  lea     rax, [rsp+6A8h+var_188]
0x1800018e4  mov     qword ptr [rsp+6A8h+StringBuffer.MinimumStaticBufferForTerminalNul], rax
0x1800018ec  xor     eax, eax
0x1800018ee  mov     [rsp+6A8h+var_188], ax
0x1800018f6  mov     dword ptr [rsp+6A8h+StringBuffer.ByteBuffer.ReservedForIMalloc], 13E0000h
0x180001901  mov     dword ptr [rsp+6A8h+var_2E8.Length], 0F800F6h
0x18000190c  lea     rax, aMicrosoftWindo; "Microsoft.Windows.SystemCompatible,vers"...
0x180001913  mov     [rsp+6A8h+var_2E8.Buffer], rax
0x18000191b  movzx   eax, word ptr [r15+8]
0x180001920  mov     [rsp+6A8h+var_2D8], ax
0x180001928  movzx   eax, word ptr [r15+0Ah]
0x18000192d  mov     [rsp+6A8h+var_2D6], ax
0x180001935  mov     rax, [r15+10h]
0x180001939  mov     [rsp+6A8h+var_2D0], rax
0x180001941  mov     [rsp+6A8h+var_2C8], 40002h
0x18000194c  mov     esi, 4
0x180001951  lea     rax, asc_180009708; "\""
0x180001958  mov     [rsp+6A8h+var_2C0], rax
0x180001960  lea     r8, [rsp+6A8h+var_2E8]; Addends
0x180001968  mov     edx, 3; NumberOfAddends
0x18000196d  lea     rcx, [rsp+6A8h+StringBuffer.ByteBuffer.ReservedForIMalloc]; StringBuffer
0x180001975  call    cs:__imp_RtlMultiAppendUnicodeStringBuffer
0x18000197c  nop     dword ptr [rax+rax+00h]
0x180001981  mov     edi, eax
0x180001983  test    eax, eax
0x180001985  js      loc_180001B14
0x18000198b  mov     [rsp+6A8h+var_4E8], esi
0x180001992  mov     [rsp+6A8h+var_4E8], 0Ch
0x18000199d  movzx   eax, word ptr [rsp+6A8h+StringBuffer.ByteBuffer.ReservedForIMalloc]
0x1800019a5  mov     word ptr [rsp+6A8h+var_450], ax
0x1800019ad  movzx   eax, word ptr [rsp+6A8h+StringBuffer.ByteBuffer.ReservedForIMalloc+2]
0x1800019b5  mov     word ptr [rsp+6A8h+var_450+2], ax
0x1800019bd  mov     eax, dword ptr [rsp+6A8h+StringBuffer.ByteBuffer.ReservedForIMalloc+4]
0x1800019c4  mov     dword ptr [rsp+6A8h+var_450+4], eax
0x1800019cb  mov     rax, qword ptr [rsp+6A8h+StringBuffer.MinimumStaticBufferForTerminalNul]
0x1800019d3  mov     [rsp+6A8h+var_448], rax
0x1800019db  movzx   eax, [rsp+6A8h+StringBuffer.String.MaximumLength]
0x1800019e3  mov     [rsp+6A8h+var_45E], ax
0x1800019eb  mov     eax, dword ptr [rsp+6A8h+StringBuffer.String+4]
0x1800019f2  mov     [rsp+6A8h+var_45C], eax
0x1800019f9  mov     rdx, [rsp+6A8h+StringBuffer.String.Buffer]
0x180001a01  mov     [rsp+6A8h+var_458], rdx
0x180001a09  mov     [rsp+6A8h+var_460], r13w
0x180001a12  mov     ecx, r13d
0x180001a15  shr     rcx, 1
0x180001a18  xor     eax, eax
0x180001a1a  mov     [rdx+rcx*2], ax
0x180001a1e  mov     [rsp+6A8h+var_4CF], 1
0x180001a26  mov     [rsp+6A8h+var_4C8], 2E002Ch
0x180001a31  mov     rax, [rsp+6A8h+var_630]
0x180001a36  mov     [rsp+6A8h+var_4C4], eax
0x180001a3d  lea     rax, aSystemDefaultC; "System Default Context"
0x180001a44  mov     [rsp+6A8h+var_4C0], rax
0x180001a4c  movzx   eax, word ptr [rsp+6A8h+var_520]
0x180001a54  mov     word ptr [rsp+6A8h+var_4E0], ax
0x180001a5c  movzx   eax, word ptr [rsp+6A8h+var_520+2]
0x180001a64  mov     word ptr [rsp+6A8h+var_4E0+2], ax
0x180001a6c  mov     eax, dword ptr [rsp+6A8h+var_520+4]
0x180001a73  mov     dword ptr [rsp+6A8h+var_4E0+4], eax
0x180001a7a  mov     rax, qword ptr [rsp+6A8h+var_520+8]
0x180001a82  mov     qword ptr [rsp+6A8h+var_4E0+8], rax
0x180001a8a  mov     [rsp+6A8h+var_4E4], bx
0x180001a92  lea     rax, [rsp+6A8h+Handle]
0x180001a97  mov     [rsp+6A8h+CommitSize], rax; __int64
0x180001a9c  xor     r9d, r9d
0x180001a9f  lea     r8, [rsp+6A8h+var_4E8]
0x180001aa7  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180001aae  mov     rcx, rdx; SourceProcessHandle
0x180001ab1  call    BaseSrvSxsCreateActivationContextFromStructEx
0x180001ab6  mov     edi, eax
0x180001ab8  test    eax, eax
0x180001aba  js      short loc_180001B14
0x180001abc  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection; CriticalSection
0x180001ac3  call    cs:__imp_RtlEnterCriticalSection
0x180001aca  nop     dword ptr [rax+rax+00h]
0x180001acf  mov     [rsp+6A8h+var_658], 1
0x180001ad4  cmp     qword ptr [r15], 0
0x180001ad8  jnz     short loc_180001AF3
0x180001ada  mov     rax, [rsp+6A8h+Handle]
0x180001adf  mov     [r15], rax
0x180001ae2  xor     edi, edi
0x180001ae4  mov     [rsp+6A8h+Handle], rdi
0x180001ae9  mov     r13, qword ptr [rsp+6A8h+var_648]
0x180001aee  jmp     loc_18000159C
0x180001af3  mov     rcx, [rsp+6A8h+Handle]; Handle
0x180001af8  call    cs:__imp_NtClose
0x180001aff  nop     dword ptr [rax+rax+00h]
0x180001b04  jmp     short loc_180001AE2
0x180001b06  cmp     ebx, 0Dh
0x180001b09  jnz     loc_1800016A9
0x180001b0f  jmp     loc_1800016A6
  ... truncated ...
```
