# p9fs::Plan9FileSystem::AddSharePath(ushort const *,ushort const *,uint)

- ea: `0x180024f90`
- end: `0x180025333`
- name: `?AddSharePath@Plan9FileSystem@p9fs@@UEAAJPEBG0I@Z`
- size: `931`
- prototype: `int(p9fs::Plan9FileSystem *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180004120`
- `0x18000c208`
- `0x18001ce4c`
- `0x18001d940`
- `0x180023460`
- `0x180024af0`
- `0x180024f90`
- `0x1800283c8`
- `0x180028718`
- `0x18002c5c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002508a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800251a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002508a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800251a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025191`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025191`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025082`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002519c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800252c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025082`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002519c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800252c3`
- `ntdll!NtOpenDirectoryObject` at `0x1800250ad`
- `ntdll!NtOpenDirectoryObject` at `0x1800250ad`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800250e4`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800250e4`
- `ntdll!RtlFreeUnicodeString` at `0x180025156`
- `ntdll!RtlFreeUnicodeString` at `0x180025156`

## string_xrefs

- `0x18002530b`: `onecore\internal\vm\inc\private\common\vml\VmPath.h`
- `0x1800252f7`: `onecore\vm\dv\storage\plan9\dll\windows\p9fs.cpp`
- `0x180025320`: `onecore\vm\dv\storage\plan9\dll\windows\p9fs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall p9fs::Plan9FileSystem::AddSharePath(
        p9fs::Plan9FileSystem *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  unsigned int v4; // r15d
  __int64 v7; // rdi
  __int64 v8; // rax
  HANDLE v9; // r14
  DWORD LastError; // ebx
  NTSTATUS v11; // eax
  int v12; // eax
  HANDLE v13; // r15
  DWORD v14; // ebx
  int v15; // eax
  const char *v16; // r9
  __int64 result; // rax
  ULONG v18; // [rsp+20h] [rbp-E8h]
  ULONG v19; // [rsp+20h] [rbp-E8h]
  struct _UNICODE_STRING UnicodeString; // [rsp+80h] [rbp-88h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-78h] BYREF
  HANDLE hObject; // [rsp+C0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v4 = a4;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  try
  {
    hObject = (HANDLE)-1LL;
    if ( v8 == 3 && !wmemcmp(a3, L"\\\\?", 3u) )
    {
      *(_QWORD *)&UnicodeString.Length = 524294;
      UnicodeString.Buffer = L"\\??";
      *(_QWORD *)&ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.Attributes, 0, 24);
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = &UnicodeString;
      v9 = hObject;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v9);
        SetLastError(LastError);
      }
      hObject = (HANDLE)-1LL;
      v11 = NtOpenDirectoryObject(&hObject, 0x80000000, &ObjectAttributes);
      if ( v11 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x2D8,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
          (const char *)(unsigned int)v11,
          v18);
    }
    else
    {
      UnicodeString = 0;
      v12 = RtlDosPathNameToNtPathName_U_WithStatus(a3, &UnicodeString, 0, 0);
      if ( v12 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x29E,
          (unsigned int)"onecore\\internal\\vm\\inc\\private\\common\\vml\\VmPath.h",
          (const char *)(unsigned int)v12,
          v18);
      memset(&ObjectAttributes, 0, 32);
      std::wstring::_Construct<1,unsigned short const *>(
        &ObjectAttributes,
        UnicodeString.Buffer,
        (unsigned __int64)UnicodeString.Length >> 1);
      RtlFreeUnicodeString(&UnicodeString);
      v13 = hObject;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v14 = GetLastError();
        CloseHandle(v13);
        SetLastError(v14);
      }
      hObject = (HANDLE)-1LL;
      *(_QWORD *)&UnicodeString.Length = 0;
      UnicodeString.Buffer = 0;
      v15 = p9fs::util::OpenRelativeFile(&hObject, 1u, 0x10u, 1u, (__int64)&UnicodeString, 0);
      if ( v15 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x2DE,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
          (const char *)(unsigned int)v15,
          v19);
      std::wstring::~wstring(&ObjectAttributes);
      v4 = a4;
    }
    *(_OWORD *)&ObjectAttributes.Length = 0;
    *(__m128i *)&ObjectAttributes.ObjectName = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(ObjectAttributes.Length) = 0;
    do
      ++v7;
    while ( a2[v7] );
    Vml::WideToMultiByte(&ObjectAttributes, a2, v7);
    p9fs::ShareList::Add((char *)this + 224, &ObjectAttributes, &hObject, v4);
    std::string::~string(&ObjectAttributes);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2E5,
                           (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x180024f90  push    rbx
0x180024f92  push    rsi
0x180024f93  push    rdi
0x180024f94  push    r12
0x180024f96  push    r13
0x180024f98  push    r14
0x180024f9a  push    r15
0x180024f9c  sub     rsp, 0D0h
0x180024fa3  mov     rax, cs:__security_cookie
0x180024faa  xor     rax, rsp
0x180024fad  mov     [rsp+108h+var_40], rax
0x180024fb5  mov     r15d, r9d
0x180024fb8  mov     [rsp+108h+var_B4], r9d
0x180024fbd  mov     rbx, r8
0x180024fc0  mov     r13, rdx
0x180024fc3  mov     [rsp+108h+var_98], rcx
0x180024fc8  xor     r12d, r12d
0x180024fcb  mov     esi, r12d
0x180024fce  mov     [rsp+108h+var_B8], r12d
0x180024fd3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180024fd7  mov     rax, rdi
0x180024fda  inc     rax
0x180024fdd  cmp     [r8+rax*2], r12w
0x180024fe2  jnz     short loc_180024FDA
0x180024fe4  mov     [rsp+108h+hObject], rdi
0x180024fec  mov     r8d, 3; N
0x180024ff2  cmp     rax, r8
0x180024ff5  jnz     loc_1800250C8
0x180024ffb  lea     rdx, asc_1800370A0; "\\\\?"
0x180025002  mov     rcx, rbx; S1
0x180025005  call    wmemcmp
0x18002500a  test    eax, eax
0x18002500c  jnz     loc_1800250C8
0x180025012  mov     qword ptr [rsp+108h+UnicodeString.Length], 80006h
0x18002501e  lea     rax, asc_1800370B8; "\\??"
0x180025025  mov     [rsp+108h+UnicodeString.Buffer], rax
0x18002502d  mov     qword ptr [rsp+108h+ObjectAttributes.Length], 30h ; '0'
0x180025039  mov     qword ptr [rsp+108h+ObjectAttributes.Attributes], r12
0x180025041  mov     [rsp+108h+ObjectAttributes.RootDirectory], r12
0x180025049  lea     rax, [rsp+108h+UnicodeString]
0x180025051  mov     [rsp+108h+ObjectAttributes.ObjectName], rax
0x180025059  xorps   xmm0, xmm0
0x18002505c  movdqu  xmmword ptr [rsp+108h+ObjectAttributes.SecurityDescriptor], xmm0
0x180025065  mov     r14, [rsp+108h+hObject]
0x18002506d  lea     rax, [r14-1]
0x180025071  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180025075  ja      short loc_180025090
0x180025077  call    cs:__imp_GetLastError
0x18002507d  mov     ebx, eax
0x18002507f  mov     rcx, r14; hObject
0x180025082  call    cs:__imp_CloseHandle
0x180025088  mov     ecx, ebx; dwErrCode
0x18002508a  call    cs:__imp_SetLastError
0x180025090  mov     [rsp+108h+hObject], rdi
0x180025098  lea     r8, [rsp+108h+ObjectAttributes]; ObjectAttributes
0x1800250a0  mov     edx, 80000000h; DesiredAccess
0x1800250a5  lea     rcx, [rsp+108h+hObject]; FileHandle
0x1800250ad  call    cs:__imp_NtOpenDirectoryObject
0x1800250b3  mov     rcx, [rsp+108h]; this
0x1800250bb  test    eax, eax
0x1800250bd  js      loc_1800252F4
0x1800250c3  jmp     loc_180025235
0x1800250c8  xorps   xmm0, xmm0
0x1800250cb  movups  xmmword ptr [rsp+108h+UnicodeString.Length], xmm0
0x1800250d3  xor     r9d, r9d
0x1800250d6  xor     r8d, r8d
0x1800250d9  lea     rdx, [rsp+108h+UnicodeString]
0x1800250e1  mov     rcx, rbx
0x1800250e4  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800250ea  mov     rcx, [rsp+108h]; this
0x1800250f2  test    eax, eax
0x1800250f4  js      loc_180025308
0x1800250fa  lea     rax, [rsp+108h+UnicodeString]
0x180025102  mov     [rsp+108h+var_A8], rax
0x180025107  mov     esi, 1
0x18002510c  mov     byte ptr [rsp+108h+var_A0], sil
0x180025111  xorps   xmm0, xmm0
0x180025114  movups  xmmword ptr [rsp+108h+ObjectAttributes.Length], xmm0
0x18002511c  mov     [rsp+108h+ObjectAttributes.ObjectName], r12
0x180025124  mov     qword ptr [rsp+108h+ObjectAttributes.Attributes], r12
0x18002512c  movzx   r8d, [rsp+108h+UnicodeString.Length]
0x180025135  shr     r8, 1
0x180025138  mov     rdx, [rsp+108h+UnicodeString.Buffer]
0x180025140  lea     rcx, [rsp+108h+ObjectAttributes]
0x180025148  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002514d  nop
0x18002514e  lea     rcx, [rsp+108h+UnicodeString]; UnicodeString
0x180025156  call    cs:__imp_RtlFreeUnicodeString
0x18002515c  nop
0x18002515d  lea     r14, [rsp+108h+ObjectAttributes]
0x180025165  cmp     qword ptr [rsp+108h+ObjectAttributes.Attributes], 7
0x18002516e  cmova   r14, qword ptr [rsp+108h+ObjectAttributes.Length]
0x180025177  mov     r12, [rsp+108h+ObjectAttributes.ObjectName]
0x18002517f  mov     r15, [rsp+108h+hObject]
0x180025187  lea     rax, [r15-1]
0x18002518b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002518f  ja      short loc_1800251AA
0x180025191  call    cs:__imp_GetLastError
0x180025197  mov     ebx, eax
0x180025199  mov     rcx, r15; hObject
0x18002519c  call    cs:__imp_CloseHandle
0x1800251a2  mov     ecx, ebx; dwErrCode
0x1800251a4  call    cs:__imp_SetLastError
0x1800251aa  mov     [rsp+108h+hObject], rdi
0x1800251b2  mov     qword ptr [rsp+108h+UnicodeString.Length], 0
0x1800251be  mov     [rsp+108h+UnicodeString.Buffer], 0
0x1800251ca  mov     [rsp+108h+var_A8], r14
0x1800251cf  mov     [rsp+108h+var_A0], r12
0x1800251d4  xor     r12d, r12d
0x1800251d7  mov     [rsp+108h+var_C8], r12; __int64
0x1800251dc  lea     rax, [rsp+108h+UnicodeString]
0x1800251e4  mov     [rsp+108h+var_D0], rax; __int64
0x1800251e9  mov     [rsp+108h+var_D8], esi; ULONG
0x1800251ed  mov     [rsp+108h+var_E0], 10h; ULONG
0x1800251f5  mov     [rsp+108h+var_E8], esi; int
0x1800251f9  mov     r9d, 80000000h
0x1800251ff  lea     r8, [rsp+108h+var_A8]
0x180025204  xor     edx, edx
0x180025206  lea     rcx, [rsp+108h+hObject]; FileHandle
0x18002520e  call    ?OpenRelativeFile@util@p9fs@@YAJPEAPEAXPEAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@KKKKV?$span@W4byte@gsl@@$0?0@gsl@@PEA_K@Z; p9fs::util::OpenRelativeFile(void * *,void *,std::basic_string_view<ushort>,ulong,ulong,ulong,ulong,gsl::span<gsl::byte,-1>,unsigned __int64 *)
0x180025213  mov     rcx, [rsp+108h]; this
0x18002521b  test    eax, eax
0x18002521d  js      loc_18002531D
0x180025223  lea     rcx, [rsp+108h+ObjectAttributes]
0x18002522b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025230  mov     r15d, [rsp+108h+var_B4]
0x180025235  mov     rbx, [rsp+108h+var_98]
0x18002523a  xorps   xmm0, xmm0
0x18002523d  movups  xmmword ptr [rsp+108h+ObjectAttributes.Length], xmm0
0x180025245  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18002524d  movdqu  xmmword ptr [rsp+108h+ObjectAttributes.ObjectName], xmm1
0x180025256  mov     byte ptr [rsp+108h+ObjectAttributes.Length], r12b
0x18002525e  or      esi, 2
0x180025261  mov     [rsp+108h+var_B8], esi
0x180025265  inc     rdi
0x180025268  cmp     [r13+rdi*2+0], r12w
0x18002526e  jnz     short loc_180025265
0x180025270  mov     r8, rdi; cchWideChar
0x180025273  mov     rdx, r13; lpWideCharStr
0x180025276  lea     rcx, [rsp+108h+ObjectAttributes]; Src
0x18002527e  call    ?WideToMultiByte@Vml@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG_KI@Z; Vml::WideToMultiByte(std::string &,ushort const *,unsigned __int64,uint)
0x180025283  mov     r9d, r15d
0x180025286  lea     r8, [rsp+108h+hObject]
0x18002528e  lea     rdx, [rsp+108h+ObjectAttributes]
0x180025296  lea     rcx, [rbx+0E0h]
0x18002529d  call    ?Add@ShareList@p9fs@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@W4Plan9ShareFlags@Storage@Resources@VirtualMachines@Schema@@@Z; p9fs::ShareList::Add(std::string const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,Schema::VirtualMachines::Resources::Storage::Plan9ShareFlags)
0x1800252a2  nop
0x1800252a3  lea     rcx, [rsp+108h+ObjectAttributes]
0x1800252ab  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800252b0  nop
0x1800252b1  mov     rcx, [rsp+108h+hObject]; hObject
0x1800252b9  lea     rax, [rcx-1]
0x1800252bd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800252c1  ja      short loc_1800252C9
0x1800252c3  call    cs:__imp_CloseHandle
0x1800252c9  xor     eax, eax
0x1800252cb  jmp     short loc_1800252D1
0x1800252cd  mov     eax, [rsp+108h+var_B8]
0x1800252d1  mov     rcx, [rsp+108h+var_40]
0x1800252d9  xor     rcx, rsp; StackCookie
0x1800252dc  call    __security_check_cookie
0x1800252e1  add     rsp, 0D0h
0x1800252e8  pop     r15
0x1800252ea  pop     r14
0x1800252ec  pop     r13
0x1800252ee  pop     r12
0x1800252f0  pop     rdi
0x1800252f1  pop     rsi
0x1800252f2  pop     rbx
0x1800252f3  retn
0x1800252f4  mov     r9d, eax; char *
0x1800252f7  lea     r8, aOnecoreVmDvSto_8; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x1800252fe  mov     edx, 2D8h; void *
0x180025303  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180025308  mov     r9d, eax; char *
0x18002530b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\vm\\inc\\private\\co"...
0x180025312  mov     edx, 29Eh; void *
0x180025317  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002531d  mov     r9d, eax; char *
0x180025320  lea     r8, aOnecoreVmDvSto_8; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180025327  mov     edx, 2DEh; void *
0x18002532c  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
