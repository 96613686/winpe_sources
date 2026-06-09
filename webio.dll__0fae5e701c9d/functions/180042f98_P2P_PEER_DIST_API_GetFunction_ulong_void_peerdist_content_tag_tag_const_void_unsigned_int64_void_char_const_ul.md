# P2P_PEER_DIST_API::GetFunction<ulong (*)(void *,peerdist_content_tag_tag const *,void *,unsigned __int64,void * *)>(char const *,ulong (*&)(void *,peerdist_content_tag_tag const *,void *,unsigned __int64,void * *))

- ea: `0x180042f98`
- end: `0x18004305d`
- name: `??$GetFunction@P6AKPEAXPEBUpeerdist_content_tag_tag@@0_KPEAPEAX@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKPEAXPEBUpeerdist_content_tag_tag@@1_KPEAPEAX@Z@Z`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180042968`

## callees

- `0x180042f98`
- `0x180043840`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004302b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004302b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043017`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043017`

## string_xrefs

- `0x180042fd6`: `ClientOpenContent`

## pseudocode

```c
__int64 __fastcall P2P_PEER_DIST_API::GetFunction<unsigned long (*)(void *,peerdist_content_tag_tag const *,void *,unsigned __int64,void * *)>(
        __int64 a1,
        __int64 a2,
        FARPROC *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  FARPROC ProcAddress; // rax
  __int64 v8; // [rsp+30h] [rbp-138h] BYREF
  char v9; // [rsp+38h] [rbp-130h]
  CHAR ProcName[272]; // [rsp+40h] [rbp-128h] BYREF

  v9 = aPeerdist[8];
  *a3 = 0;
  v8 = *(_QWORD *)"PeerDist";
  v4 = StringCchPrintfA(ProcName, 0x104u, "%s%s", (const char *)&v8, "ClientOpenContent");
  if ( v4 >= 0 )
  {
    v5 = 0;
    ProcAddress = GetProcAddress(hModule, ProcName);
    *a3 = ProcAddress;
    if ( !ProcAddress )
      return GetLastError();
  }
  else
  {
    return (unsigned __int16)v4;
  }
  return v5;
}

```

## disassembly

```asm
0x180042f98  mov     [rsp+arg_0], rbx
0x180042f9d  push    rdi
0x180042f9e  sub     rsp, 160h
0x180042fa5  mov     rax, cs:__security_cookie
0x180042fac  xor     rax, rsp
0x180042faf  mov     [rsp+168h+var_18], rax
0x180042fb7  mov     al, byte ptr cs:aPeerdist+8; ""
0x180042fbd  lea     r9, [rsp+168h+var_138]
0x180042fc2  movsd   xmm0, qword ptr cs:aPeerdist; "PeerDist"
0x180042fca  lea     rcx, [rsp+168h+ProcName]; char *
0x180042fcf  mov     [rsp+168h+var_130], al
0x180042fd3  mov     rdi, r8
0x180042fd6  lea     rax, aClientopencont; "ClientOpenContent"
0x180042fdd  mov     qword ptr [r8], 0
0x180042fe4  lea     r8, aSS; "%s%s"
0x180042feb  mov     [rsp+168h+var_148], rax
0x180042ff0  mov     edx, 104h; unsigned __int64
0x180042ff5  movsd   [rsp+168h+var_138], xmm0
0x180042ffb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180043000  test    eax, eax
0x180043002  jns     short loc_180043009
0x180043004  movzx   ebx, ax
0x180043007  jmp     short loc_180043039
0x180043009  mov     rcx, cs:hModule; hModule
0x180043010  lea     rdx, [rsp+168h+ProcName]; lpProcName
0x180043015  xor     ebx, ebx
0x180043017  call    cs:__imp_GetProcAddress
0x18004301e  nop     dword ptr [rax+rax+00h]
0x180043023  mov     [rdi], rax
0x180043026  test    rax, rax
0x180043029  jnz     short loc_180043039
0x18004302b  call    cs:__imp_GetLastError
0x180043032  nop     dword ptr [rax+rax+00h]
0x180043037  mov     ebx, eax
0x180043039  mov     eax, ebx
0x18004303b  mov     rcx, [rsp+168h+var_18]
0x180043043  xor     rcx, rsp; StackCookie
0x180043046  call    __security_check_cookie
0x18004304b  mov     rbx, [rsp+168h+arg_0]
0x180043053  add     rsp, 160h
0x18004305a  pop     rdi
0x18004305b  retn
```
