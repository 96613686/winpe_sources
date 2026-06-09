# P2P_PEER_DIST_API::GetFunction<ulong (*)(void *,void *,_OVERLAPPED *)>(char const *,ulong (*&)(void *,void *,_OVERLAPPED *))

- ea: `0x180043064`
- end: `0x180043129`
- name: `??$GetFunction@P6AKPEAX0PEAU_OVERLAPPED@@@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKPEAX1PEAU_OVERLAPPED@@@Z@Z`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180042968`

## callees

- `0x180043064`
- `0x180043840`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800430f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800430f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800430e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800430e3`

## string_xrefs

- `0x1800430a2`: `ClientCompleteContentInformation`

## pseudocode

```c
__int64 __fastcall P2P_PEER_DIST_API::GetFunction<unsigned long (*)(void *,void *,_OVERLAPPED *)>(
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
  v4 = StringCchPrintfA(ProcName, 0x104u, "%s%s", (const char *)&v8, "ClientCompleteContentInformation");
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
0x180043064  mov     [rsp+arg_0], rbx
0x180043069  push    rdi
0x18004306a  sub     rsp, 160h
0x180043071  mov     rax, cs:__security_cookie
0x180043078  xor     rax, rsp
0x18004307b  mov     [rsp+168h+var_18], rax
0x180043083  mov     al, byte ptr cs:aPeerdist+8; ""
0x180043089  lea     r9, [rsp+168h+var_138]
0x18004308e  movsd   xmm0, qword ptr cs:aPeerdist; "PeerDist"
0x180043096  lea     rcx, [rsp+168h+ProcName]; char *
0x18004309b  mov     [rsp+168h+var_130], al
0x18004309f  mov     rdi, r8
0x1800430a2  lea     rax, aClientcomplete; "ClientCompleteContentInformation"
0x1800430a9  mov     qword ptr [r8], 0
0x1800430b0  lea     r8, aSS; "%s%s"
0x1800430b7  mov     [rsp+168h+var_148], rax
0x1800430bc  mov     edx, 104h; unsigned __int64
0x1800430c1  movsd   [rsp+168h+var_138], xmm0
0x1800430c7  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800430cc  test    eax, eax
0x1800430ce  jns     short loc_1800430D5
0x1800430d0  movzx   ebx, ax
0x1800430d3  jmp     short loc_180043105
0x1800430d5  mov     rcx, cs:hModule; hModule
0x1800430dc  lea     rdx, [rsp+168h+ProcName]; lpProcName
0x1800430e1  xor     ebx, ebx
0x1800430e3  call    cs:__imp_GetProcAddress
0x1800430ea  nop     dword ptr [rax+rax+00h]
0x1800430ef  mov     [rdi], rax
0x1800430f2  test    rax, rax
0x1800430f5  jnz     short loc_180043105
0x1800430f7  call    cs:__imp_GetLastError
0x1800430fe  nop     dword ptr [rax+rax+00h]
0x180043103  mov     ebx, eax
0x180043105  mov     eax, ebx
0x180043107  mov     rcx, [rsp+168h+var_18]
0x18004310f  xor     rcx, rsp; StackCookie
0x180043112  call    __security_check_cookie
0x180043117  mov     rbx, [rsp+168h+arg_0]
0x18004311f  add     rsp, 160h
0x180043126  pop     rdi
0x180043127  retn
```
