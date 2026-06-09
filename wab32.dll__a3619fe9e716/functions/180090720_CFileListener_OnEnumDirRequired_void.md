# CFileListener::OnEnumDirRequired(void)

- ea: `0x180090720`
- end: `0x1800907db`
- name: `?OnEnumDirRequired@CFileListener@@UEAAXXZ`
- size: `187`
- prototype: `void __fastcall(CFileListener *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18007c4f0`
- `0x180085d38`
- `0x180090720`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `KERNEL32!GetFileAttributesExW` at `0x18009077a`
- `KERNEL32!GetFileAttributesExW` at `0x18009077a`
- `KERNEL32!GetLastError` at `0x180090784`
- `KERNEL32!GetLastError` at `0x180090784`
- `KERNEL32!CompareFileTime` at `0x180090795`
- `KERNEL32!CompareFileTime` at `0x180090795`

## pseudocode

```c
void __fastcall CFileListener::OnEnumDirRequired(CFileListener *this)
{
  const WCHAR *v2; // rcx
  void (__fastcall ***v3)(_QWORD, _QWORD); // rcx
  _BYTE v4[8]; // [rsp+20h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+28h] [rbp-40h] BYREF
  FILETIME FileTime1[2]; // [rsp+38h] [rbp-30h] BYREF
  int v7; // [rsp+48h] [rbp-20h]

  CStackRefCount<CConnectionPoint>::CStackRefCount<CConnectionPoint>(v4, (char *)this - 40);
  v2 = &Str;
  v7 = 0;
  FileInformation = 0;
  *(_OWORD *)&FileTime1[0].dwLowDateTime = 0;
  if ( *((_DWORD *)this + 276) )
    v2 = (const WCHAR *)*((_QWORD *)this + 139);
  if ( GetFileAttributesExW(v2, GetFileExInfoStandard, &FileInformation) )
  {
    if ( CompareFileTime((const FILETIME *)&FileTime1[0].dwHighDateTime, (const FILETIME *)this + 3) )
    {
      v3 = (void (__fastcall ***)(_QWORD, _QWORD))*((_QWORD *)this + 1);
      *((FILETIME *)this + 3) = *(FILETIME *)&FileTime1[0].dwHighDateTime;
      (**v3)(v3, 0);
    }
  }
  else
  {
    GetLastError();
  }
  CStackRefCount<CContact>::~CStackRefCount<CContact>(v4);
}

```

## disassembly

```asm
0x180090720  mov     [rsp+arg_8], rbx
0x180090725  push    rdi
0x180090726  sub     rsp, 60h
0x18009072a  mov     rax, cs:__security_cookie
0x180090731  xor     rax, rsp
0x180090734  mov     [rsp+68h+var_18], rax
0x180090739  mov     rbx, rcx
0x18009073c  lea     rdx, [rcx-28h]
0x180090740  lea     rcx, [rsp+68h+var_48]
0x180090745  call    ??0?$CStackRefCount@VCConnectionPoint@@@@QEAA@PEAVCConnectionPoint@@@Z; CStackRefCount<CConnectionPoint>::CStackRefCount<CConnectionPoint>(CConnectionPoint *)
0x18009074a  xor     eax, eax
0x18009074c  lea     rcx, Str
0x180090753  xorps   xmm0, xmm0
0x180090756  mov     [rsp+68h+var_20], eax
0x18009075a  movups  [rsp+68h+FileInformation], xmm0
0x18009075f  movups  xmmword ptr [rsp+68h+FileTime1.dwLowDateTime], xmm0
0x180090764  cmp     [rbx+450h], eax
0x18009076a  jz      short loc_180090773
0x18009076c  mov     rcx, [rbx+458h]; lpFileName
0x180090773  lea     r8, [rsp+68h+FileInformation]; lpFileInformation
0x180090778  xor     edx, edx; fInfoLevelId
0x18009077a  call    cs:__imp_GetFileAttributesExW
0x180090780  test    eax, eax
0x180090782  jnz     short loc_18009078C
0x180090784  call    cs:__imp_GetLastError
0x18009078a  jmp     short loc_1800907B9
0x18009078c  lea     rdx, [rbx+18h]; lpFileTime2
0x180090790  lea     rcx, [rsp+68h+FileTime1.dwHighDateTime]; lpFileTime1
0x180090795  call    cs:__imp_CompareFileTime
0x18009079b  test    eax, eax
0x18009079d  jz      short loc_1800907B9
0x18009079f  mov     rax, qword ptr [rsp+68h+FileTime1.dwHighDateTime]
0x1800907a4  xor     edx, edx
0x1800907a6  mov     rcx, [rbx+8]
0x1800907aa  mov     [rbx+18h], rax
0x1800907ae  mov     rax, [rcx]
0x1800907b1  mov     rax, [rax]
0x1800907b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800907b9  lea     rcx, [rsp+68h+var_48]
0x1800907be  call    ??1?$CStackRefCount@VCContact@@@@QEAA@XZ; CStackRefCount<CContact>::~CStackRefCount<CContact>(void)
0x1800907c3  mov     rcx, [rsp+68h+var_18]
0x1800907c8  xor     rcx, rsp; StackCookie
0x1800907cb  call    __security_check_cookie
0x1800907d0  mov     rbx, [rsp+68h+arg_8]
0x1800907d5  add     rsp, 60h
0x1800907d9  pop     rdi
0x1800907da  retn
```
