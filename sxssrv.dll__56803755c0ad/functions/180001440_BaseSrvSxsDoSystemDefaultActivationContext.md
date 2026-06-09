# BaseSrvSxsDoSystemDefaultActivationContext

- ea: `0x180001440`
- end: `0x180001cc6`
- name: `BaseSrvSxsDoSystemDefaultActivationContext`
- size: `2182`
- prototype: `__int64 __fastcall(unsigned __int16, union _LARGE_INTEGER, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001cd0`

## callees

- `0x180001340`
- `0x180001440`
- `0x180003170`
- `0x180006c13`
- `0x180006c30`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18000156d`
- `ntdll!RtlEnterCriticalSection` at `0x180001a41`
- `ntdll!RtlEnterCriticalSection` at `0x18000156d`
- `ntdll!RtlEnterCriticalSection` at `0x180001a41`
- `ntdll!RtlLeaveCriticalSection` at `0x180001608`
- `ntdll!RtlLeaveCriticalSection` at `0x1800016f9`
- `ntdll!RtlLeaveCriticalSection` at `0x180001bd0`
- `ntdll!RtlLeaveCriticalSection` at `0x180006cfa`
- `ntdll!RtlLeaveCriticalSection` at `0x180001608`
- `ntdll!RtlLeaveCriticalSection` at `0x1800016f9`
- `ntdll!RtlLeaveCriticalSection` at `0x180001bd0`
- `ntdll!RtlLeaveCriticalSection` at `0x180006cfa`
- `ntdll!NtClose` at `0x180001a76`
- `ntdll!NtClose` at `0x180001a76`
- `ntdll!DbgPrintEx` at `0x180006e9c`
- `ntdll!DbgPrintEx` at `0x180006e9c`
- `ntdll!NtWriteVirtualMemory` at `0x180001651`
- `ntdll!NtWriteVirtualMemory` at `0x1800016b9`
- `ntdll!NtWriteVirtualMemory` at `0x180001651`
- `ntdll!NtWriteVirtualMemory` at `0x1800016b9`
- `ntdll!NtUnmapViewOfSection` at `0x180001bbb`
- `ntdll!NtUnmapViewOfSection` at `0x180006eb9`
- `ntdll!NtUnmapViewOfSection` at `0x180001bbb`
- `ntdll!NtUnmapViewOfSection` at `0x180006eb9`
- `ntdll!RtlpApplyLengthFunction` at `0x180001804`
- `ntdll!RtlpApplyLengthFunction` at `0x180001804`
- `ntdll!RtlGetLengthWithoutTrailingPathSeperators` at `0x1800017ee`
- `ntdll!RtlFreeUnicodeString` at `0x180001bfe`
- `ntdll!RtlFreeUnicodeString` at `0x180001c4f`
- `ntdll!RtlFreeUnicodeString` at `0x180001c8d`
- `ntdll!RtlFreeUnicodeString` at `0x180006d3a`
- `ntdll!RtlFreeUnicodeString` at `0x180006dba`
- `ntdll!RtlFreeUnicodeString` at `0x180006e3a`
- `ntdll!RtlFreeUnicodeString` at `0x180001bfe`
- `ntdll!RtlFreeUnicodeString` at `0x180001c4f`
- `ntdll!RtlFreeUnicodeString` at `0x180001c8d`
- `ntdll!RtlFreeUnicodeString` at `0x180006d3a`
- `ntdll!RtlFreeUnicodeString` at `0x180006dba`
- `ntdll!RtlFreeUnicodeString` at `0x180006e3a`
- `ntdll!RtlMultiAppendUnicodeStringBuffer` at `0x180001873`
- `ntdll!RtlMultiAppendUnicodeStringBuffer` at `0x180001963`
- `ntdll!RtlMultiAppendUnicodeStringBuffer` at `0x180001873`
- `ntdll!RtlMultiAppendUnicodeStringBuffer` at `0x180001963`
- `ntdll!NtMapViewOfSection` at `0x1800015eb`
- `ntdll!NtMapViewOfSection` at `0x1800015eb`

## string_xrefs

- `0x1800018fd`: `Microsoft.Windows.SystemCompatible,version="6.0.0.0",type="win32",publicKeyToken="6595b64144ccf1df",processorArchitecture="`

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
  int LanguageFallbacks; // edi
  void *v10; // rcx
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
  UNICODE_STRING String; // [rsp+248h] [rbp-460h]
  __int128 v53; // [rsp+258h] [rbp-450h]
  UNICODE_STRING v54; // [rsp+3C0h] [rbp-2E8h] BYREF
  __int16 v55; // [rsp+3D0h] [rbp-2D8h]
  __int16 v56; // [rsp+3D2h] [rbp-2D6h]
  __int64 v57; // [rsp+3D8h] [rbp-2D0h]
  int v58; // [rsp+3E0h] [rbp-2C8h]
  const wchar_t *v59; // [rsp+3E8h] [rbp-2C0h]
  _WORD v60[24]; // [rsp+3F0h] [rbp-2B8h] BYREF
  _WORD v61[128]; // [rsp+420h] [rbp-288h] BYREF
  _WORD v62[160]; // [rsp+520h] [rbp-188h] BYREF

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
  LanguageFallbacks = -1073741823;
  if ( v6 )
  {
    RtlEnterCriticalSection(&BaseSrvSxsSystemDefaultActivationContextCriticalSection);
    if ( !*v6 )
    {
      RtlLeaveCriticalSection(&BaseSrvSxsSystemDefaultActivationContextCriticalSection);
      v33 = 256;
      *(_QWORD *)&v42 = v61;
      *(_QWORD *)&v43 = 256;
      *((_QWORD *)&v42 + 1) = v61;
      *((_QWORD *)&v43 + 1) = 256;
      *((_QWORD *)&v41 + 1) = v61;
      v61[0] = 0;
      LODWORD(v41) = 0x1000000;
      LanguageFallbacks = BasepSxsGetLanguageFallbacks(256, &v41);
      if ( LanguageFallbacks < 0 )
        goto LABEL_32;
      v34 = 46;
      StringBuffer.ByteBuffer.Buffer = (PUCHAR)v60;
      StringBuffer.ByteBuffer.Size = 46;
      StringBuffer.ByteBuffer.StaticBuffer = (PUCHAR)v60;
      StringBuffer.ByteBuffer.StaticSize = 46;
      StringBuffer.String.Buffer = v60;
      v60[0] = 0;
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
      *(_QWORD *)&v38 = v62;
      *(_QWORD *)&v39 = 318;
      *((_QWORD *)&v38 + 1) = v62;
      *((_QWORD *)&v39 + 1) = 318;
      *(_QWORD *)&StringBuffer.MinimumStaticBufferForTerminalNul = v62;
      v62[0] = 0;
      LODWORD(StringBuffer.ByteBuffer.ReservedForIMalloc) = 20840448;
      *(_DWORD *)&v54.Length = 16253174;
      v54.Buffer = L"Microsoft.Windows.SystemCompatible,version=\"6.0.0.0\",type=\"win32\",publicKeyToken=\"6595b64144ccf1"
                    "df\",processorArchitecture=\"";
      v55 = *((_WORD *)v6 + 4);
      v56 = *((_WORD *)v6 + 5);
      v57 = v6[2];
      v58 = 262146;
      v59 = L"\"";
      LanguageFallbacks = RtlMultiAppendUnicodeStringBuffer(
                            (PRTL_UNICODE_STRING_BUFFER)&StringBuffer.ByteBuffer.ReservedForIMalloc,
                            3u,
                            &v54);
      if ( LanguageFallbacks < 0 )
        goto LABEL_31;
      v45 = 12;
      v53 = *(_OWORD *)&StringBuffer.ByteBuffer.ReservedForIMalloc;
      String = StringBuffer.String;
      String.Length = Length;
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
    v10 = (void *)*v6;
    BaseAddress = 0;
    SectionOffset.QuadPart = 0;
    LanguageFallbacks = NtMapViewOfSection(
                          v10,
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
        if ( v28 )
        {
          if ( v5 == 10 || v5 == 13 )
            v12 = 4;
          LanguageFallbacks = NtWriteVirtualMemory(QuadPart, (PVOID)(v28 + 512), &BaseAddress, v12, 0);
          if ( LanguageFallbacks >= 0 )
          {
            LanguageFallbacks = 0;
            BaseAddress = 0;
          }
        }
        else
        {
          LanguageFallbacks = 0;
          BaseAddress = 0;
        }
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
0x180001440  push    rbx
0x180001442  push    rsi
0x180001443  push    rdi
0x180001444  push    r12
0x180001446  push    r13
0x180001448  push    r14
0x18000144a  push    r15
0x18000144c  sub     rsp, 670h
0x180001453  mov     rax, cs:__security_cookie
0x18000145a  xor     rax, rsp
0x18000145d  mov     [rsp+6A8h+var_48], rax
0x180001465  mov     [rsp+6A8h+var_5E0], r9
0x18000146d  mov     [rsp+6A8h+var_5E8], r8
0x180001475  mov     r13, rdx
0x180001478  mov     qword ptr [rsp+6A8h+var_648], rdx
0x18000147d  movzx   ebx, cx
0x180001480  mov     [rsp+6A8h+var_5D8], rdx
0x180001488  xor     esi, esi
0x18000148a  mov     [rsp+6A8h+Handle], rsi
0x18000148f  mov     r15d, esi
0x180001492  xor     edx, edx; Val
0x180001494  mov     r8d, 1F8h; Size
0x18000149a  lea     rcx, [rsp+6A8h+var_4E8]; void *
0x1800014a2  call    memset_0
0x1800014a7  xorps   xmm0, xmm0
0x1800014aa  xor     eax, eax
0x1800014ac  movups  xmmword ptr [rsp+6A8h+StringBuffer.String.Length], xmm0
0x1800014b4  movups  xmmword ptr [rsp+6A8h+StringBuffer.ByteBuffer.Buffer], xmm0
0x1800014bc  movups  xmmword ptr [rsp+6A8h+StringBuffer.ByteBuffer.Size], xmm0
0x1800014c4  mov     [rsp+6A8h+StringBuffer.ByteBuffer.ReservedForAllocatedSize], rax
0x1800014cc  movups  [rsp+6A8h+UnicodeStringOrUnicodeStringBuffer], xmm0
0x1800014d4  lea     r14d, [rsi+2Eh]
0x1800014d8  mov     [rsp+6A8h+var_630], rax
0x1800014dd  movups  xmmword ptr [rsp+6A8h+StringBuffer.ByteBuffer.ReservedForIMalloc], xmm0
0x1800014e5  movups  [rsp+6A8h+var_548], xmm0
0x1800014ed  movups  [rsp+6A8h+var_538], xmm0
0x1800014f5  mov     [rsp+6A8h+var_528], rax
0x1800014fd  mov     [rsp+6A8h+BaseAddress], rsi
0x180001502  xor     r12b, r12b
0x180001505  mov     [rsp+6A8h+var_658], r12b
0x18000150a  movups  [rsp+6A8h+var_520], xmm0
0x180001512  movups  [rsp+6A8h+var_510], xmm0
0x18000151a  movups  [rsp+6A8h+var_500], xmm0
0x180001522  mov     [rsp+6A8h+var_4F0], rax
0x18000152a  mov     [rsp+6A8h+var_640], esi
0x18000152e  mov     edx, esi
0x180001530  lea     r8, SxsSystemDefaultActivationContexts
0x180001537  mov     [rsp+6A8h+var_640], edx
0x18000153b  cmp     edx, 5
0x18000153e  jz      short loc_180001555
0x180001540  mov     eax, edx
0x180001542  shl     rax, 5
0x180001546  cmp     [rax+r8+18h], ebx
0x18000154b  jz      short loc_180001551
0x18000154d  inc     edx
0x18000154f  jmp     short loc_180001537
0x180001551  lea     r15, [rax+r8]
0x180001555  mov     edi, 0C0000001h
0x18000155a  test    r15, r15
0x18000155d  cmovnz  edi, esi
0x180001560  jz      loc_180001A9C
0x180001566  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection; CriticalSection
0x18000156d  call    cs:__imp_RtlEnterCriticalSection
0x180001574  nop     dword ptr [rax+rax+00h]
0x180001579  mov     [rsp+6A8h+var_658], 1
0x18000157e  cmp     qword ptr [r15], 0
0x180001582  jz      loc_1800016F2
0x180001588  mov     esi, 4
0x18000158d  xor     edx, edx
0x18000158f  lea     r14d, [rsi-2]
0x180001593  mov     [rsp+6A8h+var_630], rdx
0x180001598  mov     [rsp+6A8h+var_598], rdx
0x1800015a0  mov     rcx, [r15]; SectionHandle
0x1800015a3  mov     qword ptr [rsp+6A8h+var_648], rdx
0x1800015a8  mov     [rsp+6A8h+BaseAddress], rdx
0x1800015ad  mov     qword ptr [rsp+6A8h+var_648], rdx
0x1800015b2  mov     [rsp+6A8h+AccessProtection], r14d; AccessProtection
0x1800015b7  mov     [rsp+6A8h+AllocationType], 400000h; AllocationType
0x1800015bf  mov     [rsp+6A8h+InheritDisposition], 1; InheritDisposition
0x1800015c7  lea     rax, [rsp+6A8h+var_630]
0x1800015cc  mov     [rsp+6A8h+ViewSize], rax; ViewSize
0x1800015d1  lea     rax, [rsp+6A8h+var_648]
0x1800015d6  mov     [rsp+6A8h+SectionOffset], rax; SectionOffset
0x1800015db  mov     [rsp+6A8h+CommitSize], rdx; CommitSize
0x1800015e0  xor     r9d, r9d; ZeroBits
0x1800015e3  lea     r8, [rsp+6A8h+BaseAddress]; BaseAddress
0x1800015e8  mov     rdx, r13; ProcessHandle
0x1800015eb  call    cs:__imp_NtMapViewOfSection
0x1800015f2  nop     dword ptr [rax+rax+00h]
0x1800015f7  mov     edi, eax
0x1800015f9  test    eax, eax
0x1800015fb  jns     loc_180001685
0x180001601  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection; CriticalSection
0x180001608  call    cs:__imp_RtlLeaveCriticalSection
0x18000160f  nop     dword ptr [rax+rax+00h]
0x180001614  xor     r12b, r12b
0x180001617  mov     [rsp+6A8h+var_658], r12b
0x18000161c  test    edi, edi
0x18000161e  js      short loc_180001663
0x180001620  cmp     ebx, 0Ah
0x180001623  jnz     loc_1800016DB
0x180001629  mov     r9, rsi; NumberOfBytesToWrite
0x18000162c  mov     r14d, 8
0x180001632  mov     rdx, [rsp+6A8h+var_5E8]
0x18000163a  add     rdx, 308h; BaseAddress
0x180001641  xor     r8d, r8d
0x180001644  mov     [rsp+6A8h+CommitSize], r8; NumberOfBytesWritten
0x180001649  lea     r8, [rsp+6A8h+BaseAddress]; Buffer
0x18000164e  mov     rcx, r13; ProcessHandle
0x180001651  call    cs:__imp_NtWriteVirtualMemory
0x180001658  nop     dword ptr [rax+rax+00h]
0x18000165d  mov     edi, eax
0x18000165f  test    eax, eax
0x180001661  jns     short loc_18000166A
0x180001663  xor     esi, esi
0x180001665  jmp     loc_180001A9C
0x18000166a  mov     rdx, [rsp+6A8h+var_5E0]
0x180001672  test    rdx, rdx
0x180001675  jnz     short loc_180001694
0x180001677  xor     esi, esi
0x180001679  mov     edi, esi
0x18000167b  mov     [rsp+6A8h+BaseAddress], rsi
0x180001680  jmp     loc_180001A9C
0x180001685  mov     rax, [rsp+6A8h+BaseAddress]
0x18000168a  mov     [rsp+6A8h+BaseAddress], rax
0x18000168f  jmp     loc_180001601
0x180001694  cmp     ebx, 0Ah
0x180001697  jnz     loc_180001A84
0x18000169d  mov     r14, rsi
0x1800016a0  add     rdx, 200h; BaseAddress
0x1800016a7  xor     esi, esi
0x1800016a9  mov     [rsp+6A8h+CommitSize], rsi; NumberOfBytesWritten
0x1800016ae  mov     r9, r14; NumberOfBytesToWrite
0x1800016b1  lea     r8, [rsp+6A8h+BaseAddress]; Buffer
0x1800016b6  mov     rcx, r13; ProcessHandle
0x1800016b9  call    cs:__imp_NtWriteVirtualMemory
0x1800016c0  nop     dword ptr [rax+rax+00h]
0x1800016c5  mov     edi, eax
0x1800016c7  test    eax, eax
0x1800016c9  js      loc_180001A9C
0x1800016cf  mov     edi, esi
0x1800016d1  mov     [rsp+6A8h+BaseAddress], rsi
0x1800016d6  jmp     loc_180001A9C
0x1800016db  cmp     ebx, 0Dh
0x1800016de  jz      loc_180001629
0x1800016e4  mov     r14d, 8
0x1800016ea  mov     r9d, r14d
0x1800016ed  jmp     loc_180001632
0x1800016f2  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection; CriticalSection
0x1800016f9  call    cs:__imp_RtlLeaveCriticalSection
0x180001700  nop     dword ptr [rax+rax+00h]
0x180001705  xor     r12b, r12b
0x180001708  mov     [rsp+6A8h+var_658], r12b
0x18000170d  mov     ecx, 100h
0x180001712  mov     [rsp+6A8h+var_5B0], rcx
0x18000171a  lea     rax, [rsp+6A8h+var_288]
0x180001722  mov     qword ptr [rsp+6A8h+var_510], rax
0x18000172a  mov     qword ptr [rsp+6A8h+var_500], rcx
0x180001732  lea     rax, [rsp+6A8h+var_288]
0x18000173a  mov     qword ptr [rsp+6A8h+var_510+8], rax
0x180001742  mov     qword ptr [rsp+6A8h+var_500+8], rcx
0x18000174a  lea     rax, [rsp+6A8h+var_288]
0x180001752  mov     qword ptr [rsp+6A8h+var_520+8], rax
0x18000175a  mov     [rsp+6A8h+var_288], si
0x180001762  mov     dword ptr [rsp+6A8h+var_520], 1000000h
0x18000176d  lea     rdx, [rsp+6A8h+var_520]
0x180001775  call    BasepSxsGetLanguageFallbacks
0x18000177a  mov     edi, eax
0x18000177c  test    eax, eax
0x18000177e  js      loc_180001A9C
0x180001784  mov     [rsp+6A8h+var_5A8], r14
0x18000178c  lea     rax, [rsp+6A8h+var_2B8]
0x180001794  mov     [rsp+6A8h+StringBuffer.ByteBuffer.Buffer], rax
0x18000179c  mov     [rsp+6A8h+StringBuffer.ByteBuffer.Size], r14
0x1800017a4  lea     rax, [rsp+6A8h+var_2B8]
0x1800017ac  mov     [rsp+6A8h+StringBuffer.ByteBuffer.StaticBuffer], rax
0x1800017b4  mov     [rsp+6A8h+StringBuffer.ByteBuffer.StaticSize], r14
0x1800017bc  lea     rax, [rsp+6A8h+var_2B8]
0x1800017c4  mov     [rsp+6A8h+StringBuffer.String.Buffer], rax
0x1800017cc  mov     [rsp+6A8h+var_2B8], si
0x1800017d4  mov     dword ptr [rsp+6A8h+StringBuffer.String.Length], 2E0000h
0x1800017df  movups  xmm0, xmmword ptr cs:BaseSrvWindowsDirectory.Length
0x1800017e6  movups  [rsp+6A8h+UnicodeStringOrUnicodeStringBuffer], xmm0
0x1800017ee  mov     r9, cs:__imp_RtlGetLengthWithoutTrailingPathSeperators; LengthFunction
0x1800017f5  lea     r8, [rsp+6A8h+UnicodeStringOrUnicodeStringBuffer]; UnicodeStringOrUnicodeStringBuffer
0x1800017fd  mov     edx, 10h; Type
0x180001802  xor     ecx, ecx; Flags
0x180001804  call    cs:__imp_RtlpApplyLengthFunction
0x18000180b  nop     dword ptr [rax+rax+00h]
0x180001810  movzx   eax, word ptr [rsp+6A8h+UnicodeStringOrUnicodeStringBuffer]
0x180001818  mov     [rsp+6A8h+Addends.Length], ax
0x180001820  movzx   eax, word ptr [rsp+6A8h+UnicodeStringOrUnicodeStringBuffer+2]
0x180001828  mov     [rsp+6A8h+Addends.MaximumLength], ax
0x180001830  mov     rax, qword ptr [rsp+6A8h+UnicodeStringOrUnicodeStringBuffer+8]
0x180001838  mov     [rsp+6A8h+Addends.Buffer], rax
0x180001840  mov     [rsp+6A8h+var_5C0], 10000Eh
0x18000184b  lea     rax, aWinsxs; "\\WinSxs"
0x180001852  mov     [rsp+6A8h+var_5B8], rax
0x18000185a  lea     r8, [rsp+6A8h+Addends]; Addends
0x180001862  mov     r14d, 2
0x180001868  mov     edx, r14d; NumberOfAddends
0x18000186b  lea     rcx, [rsp+6A8h+StringBuffer]; StringBuffer
0x180001873  call    cs:__imp_RtlMultiAppendUnicodeStringBuffer
0x18000187a  nop     dword ptr [rax+rax+00h]
0x18000187f  mov     edi, eax
0x180001881  test    eax, eax
0x180001883  js      loc_180001A9C
0x180001889  movzx   r13d, [rsp+6A8h+StringBuffer.String.Length]
0x180001892  mov     ecx, 13Eh
0x180001897  mov     [rsp+6A8h+var_5A0], rcx
0x18000189f  lea     rax, [rsp+6A8h+var_188]
0x1800018a7  mov     qword ptr [rsp+6A8h+var_548], rax
0x1800018af  mov     qword ptr [rsp+6A8h+var_538], rcx
0x1800018b7  lea     rax, [rsp+6A8h+var_188]
0x1800018bf  mov     qword ptr [rsp+6A8h+var_548+8], rax
0x1800018c7  mov     qword ptr [rsp+6A8h+var_538+8], rcx
0x1800018cf  lea     rax, [rsp+6A8h+var_188]
0x1800018d7  mov     qword ptr [rsp+6A8h+StringBuffer.MinimumStaticBufferForTerminalNul], rax
0x1800018df  mov     [rsp+6A8h+var_188], si
0x1800018e7  mov     dword ptr [rsp+6A8h+StringBuffer.ByteBuffer.ReservedForIMalloc], 13E0000h
0x1800018f2  mov     dword ptr [rsp+6A8h+var_2E8.Length], 0F800F6h
0x1800018fd  lea     rax, aMicrosoftWindo; "Microsoft.Windows.SystemCompatible,vers"...
0x180001904  mov     [rsp+6A8h+var_2E8.Buffer], rax
0x18000190c  movzx   eax, word ptr [r15+8]
0x180001911  mov     [rsp+6A8h+var_2D8], ax
0x180001919  movzx   eax, word ptr [r15+0Ah]
0x18000191e  mov     [rsp+6A8h+var_2D6], ax
0x180001926  mov     rax, [r15+10h]
0x18000192a  mov     [rsp+6A8h+var_2D0], rax
0x180001932  mov     [rsp+6A8h+var_2C8], 40002h
0x18000193d  lea     esi, [r14+2]
0x180001941  lea     rax, asc_180008708; "\""
0x180001948  mov     [rsp+6A8h+var_2C0], rax
0x180001950  lea     r8, [rsp+6A8h+var_2E8]; Addends
0x180001958  lea     edx, [rsi-1]; NumberOfAddends
0x18000195b  lea     rcx, [rsp+6A8h+StringBuffer.ByteBuffer.ReservedForIMalloc]; StringBuffer
0x180001963  call    cs:__imp_RtlMultiAppendUnicodeStringBuffer
0x18000196a  nop     dword ptr [rax+rax+00h]
0x18000196f  mov     edi, eax
0x180001971  test    eax, eax
0x180001973  js      loc_180001A92
0x180001979  mov     [rsp+6A8h+var_4E8], esi
0x180001980  mov     [rsp+6A8h+var_4E8], 0Ch
0x18000198b  movups  xmm0, xmmword ptr [rsp+6A8h+StringBuffer.ByteBuffer.ReservedForIMalloc]
0x180001993  movups  [rsp+6A8h+var_450], xmm0
0x18000199b  movups  xmm1, xmmword ptr [rsp+6A8h+StringBuffer.String.Length]
0x1800019a3  movups  [rsp+6A8h+var_460], xmm1
0x1800019ab  mov     word ptr [rsp+6A8h+var_460], r13w
0x1800019b4  mov     ecx, r13d
0x1800019b7  shr     rcx, 1
0x1800019ba  mov     rax, qword ptr [rsp+6A8h+var_460+8]
0x1800019c2  xor     r8d, r8d
0x1800019c5  mov     [rax+rcx*2], r8w
0x1800019ca  mov     [rsp+6A8h+var_4CF], 1
0x1800019d2  mov     [rsp+6A8h+var_4C8], 2E002Ch
0x1800019dd  mov     rax, [rsp+6A8h+var_630]
0x1800019e2  mov     [rsp+6A8h+var_4C4], eax
0x1800019e9  lea     rax, aSystemDefaultC; "System Default Context"
0x1800019f0  mov     [rsp+6A8h+var_4C0], rax
0x1800019f8  movups  xmm0, [rsp+6A8h+var_520]
0x180001a00  movups  [rsp+6A8h+var_4E0], xmm0
0x180001a08  mov     [rsp+6A8h+var_4E4], bx
0x180001a10  lea     rax, [rsp+6A8h+Handle]
0x180001a15  mov     [rsp+6A8h+CommitSize], rax; __int64
0x180001a1a  xor     r9d, r9d
0x180001a1d  lea     r8, [rsp+6A8h+var_4E8]
0x180001a25  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180001a2c  mov     rcx, rdx; SourceProcessHandle
0x180001a2f  call    BaseSrvSxsCreateActivationContextFromStructEx
0x180001a34  mov     edi, eax
0x180001a36  test    eax, eax
0x180001a38  js      short loc_180001A92
0x180001a3a  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection; CriticalSection
0x180001a41  call    cs:__imp_RtlEnterCriticalSection
0x180001a48  nop     dword ptr [rax+rax+00h]
0x180001a4d  mov     [rsp+6A8h+var_658], 1
0x180001a52  cmp     qword ptr [r15], 0
0x180001a56  jnz     short loc_180001A71
0x180001a58  mov     rax, [rsp+6A8h+Handle]
0x180001a5d  mov     [r15], rax
0x180001a60  xor     edx, edx
0x180001a62  mov     [rsp+6A8h+Handle], rdx
0x180001a67  mov     r13, qword ptr [rsp+6A8h+var_648]
0x180001a6c  jmp     loc_180001593
0x180001a71  mov     rcx, [rsp+6A8h+Handle]; Handle
0x180001a76  call    cs:__imp_NtClose
0x180001a7d  nop     dword ptr [rax+rax+00h]
0x180001a82  jmp     short loc_180001A60
0x180001a84  cmp     ebx, 0Dh
0x180001a87  jnz     loc_1800016A0
0x180001a8d  jmp     loc_18000169D
0x180001a92  mov     r13, qword ptr [rsp+6A8h+var_648]
0x180001a97  jmp     loc_180001663
0x180001a9c  test    r12b, r12b
0x180001a9f  jnz     loc_180001BC9
0x180001aa5  mov     rax, [rsp+6A8h+StringBuffer.ByteBuffer.Buffer]
0x180001aad  mov     rcx, [rsp+6A8h+StringBuffer.ByteBuffer.StaticBuffer]
0x180001ab5  test    rax, rax
0x180001ab8  jnz     loc_180001BE1
0x180001abe  mov     [rsp+6A8h+StringBuffer.String.Buffer], rcx
  ... truncated ...
```
