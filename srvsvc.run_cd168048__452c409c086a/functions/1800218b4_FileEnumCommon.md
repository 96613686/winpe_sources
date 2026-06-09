# FileEnumCommon

- ea: `0x1800218b4`
- end: `0x180021ac3`
- name: `FileEnumCommon`
- size: `527`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, PCWSTR@<rdx>, SIZE_T, __int64, __int64, __int64, char)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021de0`
- `0x180021ec0`

## callees

- `0x180008ca0`
- `0x18001deb0`
- `0x18001e80c`
- `0x180020de8`
- `0x1800218b4`
- `0x180021f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a0c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002192e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002192e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021a90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021a90`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180021984`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180021984`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021964`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021964`
- `ntdll!RtlInitUnicodeString` at `0x18002194a`
- `ntdll!RtlInitUnicodeString` at `0x180021957`
- `ntdll!RtlInitUnicodeString` at `0x180021997`
- `ntdll!RtlInitUnicodeString` at `0x18002194a`
- `ntdll!RtlInitUnicodeString` at `0x180021957`
- `ntdll!RtlInitUnicodeString` at `0x180021997`

## string_xrefs

- `0x18002195d`: `SRVSVC.DLL`

## pseudocode

```c
__int64 __fastcall FileEnumCommon(
        PCWSTR SourceString,
        PCWSTR a2,
        int a3,
        __int64 a4,
        SIZE_T a5,
        _DWORD *a6,
        _DWORD *a7,
        int *a8,
        char a9)
{
  struct _UNICODE_STRING *v13; // rax
  struct _UNICODE_STRING *v14; // rdi
  HMODULE ModuleHandleW; // rax
  HMODULE v16; // rbp
  __int64 v17; // rbx
  DWORD LastError; // eax
  __int64 v19; // rbx
  DWORD v20; // eax
  int v21; // eax
  unsigned int InfoCommon; // ebx
  SIZE_T uBytes; // [rsp+20h] [rbp-D8h]
  WCHAR Buffer[64]; // [rsp+30h] [rbp-C8h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (unsigned int)(a3 - 2) > 1 )
    return 124;
  v13 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x60u);
  v14 = v13;
  if ( !v13 )
    return 8;
  RtlInitUnicodeString(v13, SourceString);
  RtlInitUnicodeString(v14 + 1, a2);
  ModuleHandleW = GetModuleHandleW(L"SRVSVC.DLL");
  v16 = ModuleHandleW;
  if ( ModuleHandleW )
  {
    if ( LoadStringW(ModuleHandleW, 0x6Cu, Buffer, 64) )
    {
      RtlInitUnicodeString(v14 + 2, Buffer);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v17 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_Dq(v17, 10, WPP_8d4b24a7306734fa67e2fe82e9b4ddec_Traceguids, LastError, v16);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v19 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v20 = GetLastError();
    WPP_SF_d(v19, 11, WPP_8d4b24a7306734fa67e2fe82e9b4ddec_Traceguids, v20);
  }
  *(_DWORD *)&v14[4].Length = a3;
  if ( a9 )
    LODWORD(v14[4].Buffer) = 1;
  if ( a8 )
    v21 = *a8;
  else
    v21 = 0;
  HIDWORD(v14[5].Buffer) = v21;
  LODWORD(uBytes) = a5;
  InfoCommon = SsServerFsControlGetInfoCommonEx(qword_18005CDB8, 0x14600Bu, v14, uBytes);
  *a6 = *(_DWORD *)&v14[5].Length;
  *a7 = *(_DWORD *)(&v14[5].MaximumLength + 1);
  if ( *a6 )
  {
    if ( a8 )
      *a8 = HIDWORD(v14[5].Buffer);
  }
  LocalFree(v14);
  return InfoCommon;
}

```

## disassembly

```asm
0x1800218b4  mov     [rsp+arg_10], rbx
0x1800218b9  push    rbp
0x1800218ba  push    rsi
0x1800218bb  push    rdi
0x1800218bc  push    r12
0x1800218be  push    r13
0x1800218c0  push    r14
0x1800218c2  push    r15
0x1800218c4  sub     rsp, 0C0h
0x1800218cb  mov     rax, cs:__security_cookie
0x1800218d2  xor     rax, rsp
0x1800218d5  mov     [rsp+0F8h+var_48], rax
0x1800218dd  mov     r15, [rsp+0F8h+arg_28]
0x1800218e5  mov     r14d, r8d
0x1800218e8  mov     r13, [rsp+0F8h+arg_30]
0x1800218f0  mov     rbp, rdx
0x1800218f3  mov     rsi, [rsp+0F8h+arg_38]
0x1800218fb  mov     rbx, rcx
0x1800218fe  xor     edx, edx; Val
0x180021900  lea     rcx, [rsp+0F8h+Buffer]; void *
0x180021905  mov     r8d, 80h; Size
0x18002190b  mov     r12, r9
0x18002190e  call    memset_0
0x180021913  lea     eax, [r14-2]
0x180021917  cmp     eax, 1
0x18002191a  jbe     short loc_180021926
0x18002191c  mov     eax, 7Ch ; '|'
0x180021921  jmp     loc_180021A98
0x180021926  mov     edx, 60h ; '`'; uBytes
0x18002192b  lea     ecx, [rdx-20h]; uFlags
0x18002192e  call    cs:__imp_LocalAlloc
0x180021934  mov     rdi, rax
0x180021937  test    rax, rax
0x18002193a  jnz     short loc_180021944
0x18002193c  lea     eax, [rdi+8]
0x18002193f  jmp     loc_180021A98
0x180021944  mov     rdx, rbx; SourceString
0x180021947  mov     rcx, rdi; DestinationString
0x18002194a  call    cs:__imp_RtlInitUnicodeString
0x180021950  lea     rcx, [rdi+10h]; DestinationString
0x180021954  mov     rdx, rbp; SourceString
0x180021957  call    cs:__imp_RtlInitUnicodeString
0x18002195d  lea     rcx, aSrvsvcDll_1; "SRVSVC.DLL"
0x180021964  call    cs:__imp_GetModuleHandleW
0x18002196a  mov     rbp, rax
0x18002196d  test    rax, rax
0x180021970  jz      short loc_1800219E9
0x180021972  mov     r9d, 40h ; '@'; cchBufferMax
0x180021978  lea     r8, [rsp+0F8h+Buffer]; lpBuffer
0x18002197d  mov     rcx, rax; hInstance
0x180021980  lea     edx, [r9+2Ch]; uID
0x180021984  call    cs:__imp_LoadStringW
0x18002198a  test    eax, eax
0x18002198c  jz      short loc_1800219A2
0x18002198e  lea     rcx, [rdi+20h]; DestinationString
0x180021992  lea     rdx, [rsp+0F8h+Buffer]; SourceString
0x180021997  call    cs:__imp_RtlInitUnicodeString
0x18002199d  jmp     loc_180021A29
0x1800219a2  mov     rbx, cs:WPP_GLOBAL_Control
0x1800219a9  lea     rax, WPP_GLOBAL_Control
0x1800219b0  cmp     rbx, rax
0x1800219b3  jz      short loc_180021A29
0x1800219b5  test    byte ptr [rbx+1Ch], 20h
0x1800219b9  jz      short loc_180021A29
0x1800219bb  cmp     byte ptr [rbx+19h], 1
0x1800219bf  jb      short loc_180021A29
0x1800219c1  mov     rbx, [rbx+10h]
0x1800219c5  call    cs:__imp_GetLastError
0x1800219cb  mov     edx, 0Ah
0x1800219d0  mov     [rsp+0F8h+uBytes], rbp
0x1800219d5  mov     r9d, eax
0x1800219d8  lea     r8, WPP_8d4b24a7306734fa67e2fe82e9b4ddec_Traceguids
0x1800219df  mov     rcx, rbx
0x1800219e2  call    WPP_SF_Dq
0x1800219e7  jmp     short loc_180021A29
0x1800219e9  mov     rbx, cs:WPP_GLOBAL_Control
0x1800219f0  lea     rax, WPP_GLOBAL_Control
0x1800219f7  cmp     rbx, rax
0x1800219fa  jz      short loc_180021A29
0x1800219fc  test    byte ptr [rbx+1Ch], 20h
0x180021a00  jz      short loc_180021A29
0x180021a02  cmp     byte ptr [rbx+19h], 1
0x180021a06  jb      short loc_180021A29
0x180021a08  mov     rbx, [rbx+10h]
0x180021a0c  call    cs:__imp_GetLastError
0x180021a12  mov     edx, 0Bh
0x180021a17  lea     r8, WPP_8d4b24a7306734fa67e2fe82e9b4ddec_Traceguids
0x180021a1e  mov     r9d, eax
0x180021a21  mov     rcx, rbx
0x180021a24  call    WPP_SF_d
0x180021a29  cmp     [rsp+0F8h+arg_40], 0
0x180021a31  mov     [rdi+40h], r14d
0x180021a35  jz      short loc_180021A3E
0x180021a37  mov     dword ptr [rdi+48h], 1
0x180021a3e  test    rsi, rsi
0x180021a41  jz      short loc_180021A47
0x180021a43  mov     eax, [rsi]
0x180021a45  jmp     short loc_180021A49
0x180021a47  xor     eax, eax
0x180021a49  mov     [rdi+5Ch], eax
0x180021a4c  mov     r9, r12
0x180021a4f  mov     eax, dword ptr [rsp+0F8h+arg_20]
0x180021a56  mov     r8, rdi; hMem
0x180021a59  mov     rcx, cs:qword_18005CDB8; FileHandle
0x180021a60  mov     edx, 14600Bh; FsControlCode
0x180021a65  mov     dword ptr [rsp+0F8h+uBytes], eax; uBytes
0x180021a69  call    SsServerFsControlGetInfoCommonEx
0x180021a6e  mov     ecx, [rdi+50h]
0x180021a71  mov     ebx, eax
0x180021a73  mov     [r15], ecx
0x180021a76  mov     ecx, [rdi+54h]
0x180021a79  mov     [r13+0], ecx
0x180021a7d  cmp     dword ptr [r15], 0
0x180021a81  jbe     short loc_180021A8D
0x180021a83  test    rsi, rsi
0x180021a86  jz      short loc_180021A8D
0x180021a88  mov     ecx, [rdi+5Ch]
0x180021a8b  mov     [rsi], ecx
0x180021a8d  mov     rcx, rdi; hMem
0x180021a90  call    cs:__imp_LocalFree
0x180021a96  mov     eax, ebx
0x180021a98  mov     rcx, [rsp+0F8h+var_48]
0x180021aa0  xor     rcx, rsp; StackCookie
0x180021aa3  call    __security_check_cookie
0x180021aa8  mov     rbx, [rsp+0F8h+arg_10]
0x180021ab0  add     rsp, 0C0h
0x180021ab7  pop     r15
0x180021ab9  pop     r14
0x180021abb  pop     r13
0x180021abd  pop     r12
0x180021abf  pop     rdi
0x180021ac0  pop     rsi
0x180021ac1  pop     rbp
0x180021ac2  retn
```
