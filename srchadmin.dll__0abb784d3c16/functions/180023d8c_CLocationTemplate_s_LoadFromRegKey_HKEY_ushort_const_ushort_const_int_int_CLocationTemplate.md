# CLocationTemplate::s_LoadFromRegKey(HKEY__ *,ushort const *,ushort const *,int,int,CLocationTemplate * *)

- ea: `0x180023d8c`
- end: `0x180023f40`
- name: `?s_LoadFromRegKey@CLocationTemplate@@SAJPEAUHKEY__@@PEBG1HHPEAPEAV1@@Z`
- size: `436`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, __int64, int, struct CLocationTemplate **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023b94`

## callees

- `0x180005cc0`
- `0x18000d4dc`
- `0x18001a7fc`
- `0x18002184c`
- `0x180022e94`
- `0x180022efc`
- `0x180023848`
- `0x180023d8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023df7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023e00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023df7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023e00`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180023e2e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180023e2e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180023ee6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180023ee6`

## string_xrefs

- `0x180023e54`: `SavePath`

## pseudocode

```c
__int64 __fastcall CLocationTemplate::s_LoadFromRegKey(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        int a5,
        struct CLocationTemplate **a6)
{
  _DWORD *v9; // rax
  _DWORD *v10; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v12; // rax
  unsigned int v13; // edx
  int StringValue; // ebx
  unsigned int v15; // r9d
  OLECHAR sz[40]; // [rsp+50h] [rbp-298h] BYREF
  unsigned __int16 v18[264]; // [rsp+A0h] [rbp-248h] BYREF

  *a6 = 0;
  v9 = operator new(0x430u);
  v10 = v9;
  if ( v9 )
  {
    v9[134] = 1;
    CurrentProcess = GetCurrentProcess();
    v12 = GetCurrentProcess();
    if ( DuplicateHandle(v12, a1, CurrentProcess, (LPHANDLE)v10 + 133, 0, 0, 2u)
      || (StringValue = ResultFromKnownLastError(), StringValue >= 0) )
    {
      StringValue = RegGetStringValue(a1, L"SavePath", (unsigned __int16 *)v10 + 270, 0x104u);
      if ( StringValue >= 0 )
        goto LABEL_8;
      if ( RegGetIndirectStringValue(a1, L"Name", v18, v15) < 0 )
        v18[0] = 0;
      StringValue = CLocationTemplate::_ComputeFullNameAndPath((CLocationTemplate *)v10, a3, a2, v18);
      if ( StringValue >= 0 )
      {
LABEL_8:
        RegGetIndirectStringValue(a1, L"Description", (unsigned __int16 *)v10, v15);
        if ( RegGetStringValue(a1, L"FolderType", sz, 0x27u) < 0 || CLSIDFromString(sz, (LPCLSID)(v10 + 130)) < 0 )
          *(GUID *)(v10 + 130) = FOLDERTYPEID_SearchConnector;
      }
    }
    if ( StringValue < 0 )
      CLocationTemplate::`scalar deleting destructor'((CLocationTemplate *)v10, v13);
    else
      *a6 = (struct CLocationTemplate *)v10;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x180023d8c  mov     [rsp+arg_18], rbx
0x180023d91  push    rbp
0x180023d92  push    rsi
0x180023d93  push    rdi
0x180023d94  push    r14
0x180023d96  push    r15
0x180023d98  sub     rsp, 2C0h
0x180023d9f  mov     rax, cs:__security_cookie
0x180023da6  xor     rax, rsp
0x180023da9  mov     [rsp+2E8h+var_38], rax
0x180023db1  mov     r14, [rsp+2E8h+arg_28]
0x180023db9  mov     rsi, rcx
0x180023dbc  mov     ecx, 430h; unsigned __int64
0x180023dc1  mov     r15, r8
0x180023dc4  mov     rbp, rdx
0x180023dc7  mov     qword ptr [r14], 0
0x180023dce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023dd3  mov     [rsp+2E8h+var_2A8], rax
0x180023dd8  mov     rdi, rax
0x180023ddb  test    rax, rax
0x180023dde  jz      loc_180023F12
0x180023de4  test    rax, rax
0x180023de7  jz      loc_180023F12
0x180023ded  mov     dword ptr [rax+218h], 1
0x180023df7  call    cs:__imp_GetCurrentProcess
0x180023dfd  mov     rbx, rax
0x180023e00  call    cs:__imp_GetCurrentProcess
0x180023e06  mov     [rsp+2E8h+dwOptions], 2; dwOptions
0x180023e0e  lea     r9, [rdi+428h]; lpTargetHandle
0x180023e15  mov     rcx, rax; hSourceProcessHandle
0x180023e18  mov     [rsp+2E8h+bInheritHandle], 0; bInheritHandle
0x180023e20  mov     r8, rbx; hTargetProcessHandle
0x180023e23  mov     [rsp+2E8h+dwDesiredAccess], 0; dwDesiredAccess
0x180023e2b  mov     rdx, rsi; hSourceHandle
0x180023e2e  call    cs:__imp_DuplicateHandle
0x180023e34  test    eax, eax
0x180023e36  jnz     short loc_180023E47
0x180023e38  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180023e3d  mov     ebx, eax
0x180023e3f  test    eax, eax
0x180023e41  js      loc_180023EFF
0x180023e47  lea     r8, [rdi+21Ch]; unsigned __int16 *
0x180023e4e  mov     r9d, 104h; unsigned int
0x180023e54  lea     rdx, aSavepath; "SavePath"
0x180023e5b  mov     rcx, rsi; HKEY
0x180023e5e  call    ?RegGetStringValue@@YAJPEAUHKEY__@@PEBGPEAGK@Z; RegGetStringValue(HKEY__ *,ushort const *,ushort *,ulong)
0x180023e63  mov     ebx, eax
0x180023e65  test    eax, eax
0x180023e67  jns     short loc_180023EAA
0x180023e69  lea     r8, [rsp+2E8h+var_248]; unsigned __int16 *
0x180023e71  mov     rcx, rsi; HKEY
0x180023e74  lea     rdx, aName; "Name"
0x180023e7b  call    ?RegGetIndirectStringValue@@YAJPEAUHKEY__@@PEBGPEAGK@Z; RegGetIndirectStringValue(HKEY__ *,ushort const *,ushort *,ulong)
0x180023e80  test    eax, eax
0x180023e82  jns     short loc_180023E8E
0x180023e84  xor     eax, eax
0x180023e86  mov     [rsp+2E8h+var_248], ax
0x180023e8e  lea     r9, [rsp+2E8h+var_248]; unsigned __int16 *
0x180023e96  mov     r8, rbp; unsigned __int16 *
0x180023e99  mov     rdx, r15; unsigned __int16 *
0x180023e9c  mov     rcx, rdi; this
0x180023e9f  call    ?_ComputeFullNameAndPath@CLocationTemplate@@AEAAJPEBG00@Z; CLocationTemplate::_ComputeFullNameAndPath(ushort const *,ushort const *,ushort const *)
0x180023ea4  mov     ebx, eax
0x180023ea6  test    eax, eax
0x180023ea8  js      short loc_180023EFF
0x180023eaa  mov     r8, rdi; unsigned __int16 *
0x180023ead  lea     rdx, aDescription; "Description"
0x180023eb4  mov     rcx, rsi; HKEY
0x180023eb7  call    ?RegGetIndirectStringValue@@YAJPEAUHKEY__@@PEBGPEAGK@Z; RegGetIndirectStringValue(HKEY__ *,ushort const *,ushort *,ulong)
0x180023ebc  mov     r9d, 27h ; '''; unsigned int
0x180023ec2  lea     r8, [rsp+2E8h+sz]; unsigned __int16 *
0x180023ec7  lea     rdx, aFoldertype; "FolderType"
0x180023ece  mov     rcx, rsi; HKEY
0x180023ed1  call    ?RegGetStringValue@@YAJPEAUHKEY__@@PEBGPEAGK@Z; RegGetStringValue(HKEY__ *,ushort const *,ushort *,ulong)
0x180023ed6  test    eax, eax
0x180023ed8  js      short loc_180023EF0
0x180023eda  lea     rdx, [rdi+208h]; pclsid
0x180023ee1  lea     rcx, [rsp+2E8h+sz]; lpsz
0x180023ee6  call    cs:__imp_CLSIDFromString
0x180023eec  test    eax, eax
0x180023eee  jns     short loc_180023EFF
0x180023ef0  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_SearchConnector.Data1
0x180023ef7  movdqu  xmmword ptr [rdi+208h], xmm0
0x180023eff  test    ebx, ebx
0x180023f01  js      short loc_180023F08
0x180023f03  mov     [r14], rdi
0x180023f06  jmp     short loc_180023F17
0x180023f08  mov     rcx, rdi; this
0x180023f0b  call    ??_GCLocationTemplate@@QEAAPEAXI@Z; CLocationTemplate::`scalar deleting destructor'(uint)
0x180023f10  jmp     short loc_180023F17
0x180023f12  mov     ebx, 8007000Eh
0x180023f17  mov     eax, ebx
0x180023f19  mov     rcx, [rsp+2E8h+var_38]
0x180023f21  xor     rcx, rsp; StackCookie
0x180023f24  call    __security_check_cookie
0x180023f29  mov     rbx, [rsp+2E8h+arg_18]
0x180023f31  add     rsp, 2C0h
0x180023f38  pop     r15
0x180023f3a  pop     r14
0x180023f3c  pop     rdi
0x180023f3d  pop     rsi
0x180023f3e  pop     rbp
0x180023f3f  retn
```
