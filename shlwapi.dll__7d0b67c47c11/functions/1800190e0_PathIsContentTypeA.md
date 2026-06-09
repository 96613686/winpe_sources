# PathIsContentTypeA

- ea: `0x1800190e0`
- end: `0x18001917e`
- name: `PathIsContentTypeA`
- size: `158`
- prototype: `BOOL __stdcall(LPCSTR pszPath, LPCSTR pszContentType)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180012550`
- `0x1800190e0`
- `0x180020250`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionA` at `0x180019109`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionA` at `0x180019109`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180019150`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180019150`

## pseudocode

```c
BOOL __stdcall PathIsContentTypeA(LPCSTR pszPath, LPCSTR pszContentType)
{
  BOOL v2; // ebx
  const CHAR *ExtensionA; // rax
  DWORD pcchOut[4]; // [rsp+30h] [rbp-138h] BYREF
  CHAR String1[272]; // [rsp+40h] [rbp-128h] BYREF

  v2 = 0;
  if ( pszPath )
  {
    ExtensionA = PathFindExtensionA(pszPath);
    if ( ExtensionA )
    {
      if ( *ExtensionA )
      {
        pcchOut[0] = 260;
        if ( AssocQueryStringA(0, ASSOCSTR_CONTENTTYPE, ExtensionA, 0, String1, pcchOut) >= 0 )
          LOBYTE(v2) = lstrcmpiA(String1, pszContentType) == 0;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800190e0  mov     [rsp+arg_10], rbx
0x1800190e5  push    rdi
0x1800190e6  sub     rsp, 160h
0x1800190ed  mov     rax, cs:__security_cookie
0x1800190f4  xor     rax, rsp
0x1800190f7  mov     [rsp+168h+var_18], rax
0x1800190ff  xor     ebx, ebx
0x180019101  mov     rdi, rdx
0x180019104  test    rcx, rcx
0x180019107  jz      short loc_18001915B
0x180019109  call    cs:__imp_PathFindExtensionA
0x18001910f  test    rax, rax
0x180019112  jz      short loc_18001915B
0x180019114  cmp     [rax], bl
0x180019116  jz      short loc_18001915B
0x180019118  lea     rcx, [rsp+168h+var_138]
0x18001911d  mov     [rsp+168h+var_138], 104h
0x180019125  mov     [rsp+168h+pcchOut], rcx; pcchOut
0x18001912a  lea     edx, [rbx+0Eh]; str
0x18001912d  lea     rcx, [rsp+168h+String1]
0x180019132  xor     r9d, r9d; pszExtra
0x180019135  mov     [rsp+168h+pszOut], rcx; pszOut
0x18001913a  mov     r8, rax; pszAssoc
0x18001913d  xor     ecx, ecx; flags
0x18001913f  call    AssocQueryStringA
0x180019144  test    eax, eax
0x180019146  js      short loc_18001915B
0x180019148  mov     rdx, rdi; lpString2
0x18001914b  lea     rcx, [rsp+168h+String1]; lpString1
0x180019150  call    cs:__imp_lstrcmpiA
0x180019156  test    eax, eax
0x180019158  setz    bl
0x18001915b  mov     eax, ebx
0x18001915d  mov     rcx, [rsp+168h+var_18]
0x180019165  xor     rcx, rsp; StackCookie
0x180019168  call    __security_check_cookie
0x18001916d  mov     rbx, [rsp+168h+arg_10]
0x180019175  add     rsp, 160h
0x18001917c  pop     rdi
0x18001917d  retn
```
