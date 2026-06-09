# PathUndecorateA

- ea: `0x180019820`
- end: `0x1800198ea`
- name: `PathUndecorateA`
- size: `202`
- prototype: `void __stdcall(LPSTR pszPath)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800181ac`
- `0x180019820`
- `0x1800369dd`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionA` at `0x18001983b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionA` at `0x18001983b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800198c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800198c5`

## pseudocode

```c
void __stdcall PathUndecorateA(LPSTR pszPath)
{
  LPSTR ExtensionA; // rax
  const CHAR *v3; // rsi
  char *v4; // rdi
  CHAR *v5; // rdx
  int v6; // eax

  if ( pszPath )
  {
    ExtensionA = PathFindExtensionA(pszPath);
    v3 = ExtensionA;
    if ( ExtensionA > pszPath && *(ExtensionA - 1) == 93 )
    {
      v4 = ExtensionA - 2;
      if ( ExtensionA - 2 > pszPath && !(unsigned int)IsTrailByte(pszPath, ExtensionA - 1) )
      {
        do
        {
          if ( (unsigned __int8)(*v4 - 48) > 9u )
            break;
          --v4;
        }
        while ( v4 > pszPath );
        if ( !(unsigned int)IsTrailByte(pszPath, v4 + 1)
          && *v4 == 91
          && v4 > pszPath
          && !(unsigned int)IsTrailByte(pszPath, v4) )
        {
          v5 = v4 - 1;
          if ( *(v4 - 1) != 92 || v5 != pszPath && (unsigned int)IsTrailByte(pszPath, v5) )
          {
            v6 = lstrlenA(v3);
            memmove_0(v4, v3, (unsigned int)(v6 + 1));
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180019820  test    rcx, rcx
0x180019823  jz      locret_1800198E9
0x180019829  mov     [rsp+arg_0], rbx
0x18001982e  mov     [rsp+arg_8], rsi
0x180019833  push    rdi
0x180019834  sub     rsp, 20h
0x180019838  mov     rbx, rcx
0x18001983b  call    cs:__imp_PathFindExtensionA
0x180019841  mov     rsi, rax
0x180019844  cmp     rax, rbx
0x180019847  jbe     loc_1800198DA
0x18001984d  lea     rdx, [rax-1]; char *
0x180019851  cmp     byte ptr [rdx], 5Dh ; ']'
0x180019854  jnz     loc_1800198DA
0x18001985a  lea     rdi, [rdx-1]
0x18001985e  cmp     rdi, rbx
0x180019861  jbe     short loc_1800198DA
0x180019863  mov     rcx, rbx; char *
0x180019866  call    ?IsTrailByte@@YAHPEBD0@Z; IsTrailByte(char const *,char const *)
0x18001986b  test    eax, eax
0x18001986d  jnz     short loc_1800198DA
0x18001986f  mov     al, [rdi]
0x180019871  sub     al, 30h ; '0'
0x180019873  cmp     al, 9
0x180019875  ja      short loc_18001987F
0x180019877  dec     rdi
0x18001987a  cmp     rdi, rbx
0x18001987d  ja      short loc_18001986F
0x18001987f  lea     rdx, [rdi+1]; char *
0x180019883  mov     rcx, rbx; char *
0x180019886  call    ?IsTrailByte@@YAHPEBD0@Z; IsTrailByte(char const *,char const *)
0x18001988b  test    eax, eax
0x18001988d  jnz     short loc_1800198DA
0x18001988f  cmp     byte ptr [rdi], 5Bh ; '['
0x180019892  jnz     short loc_1800198DA
0x180019894  cmp     rdi, rbx
0x180019897  jbe     short loc_1800198DA
0x180019899  mov     rdx, rdi; char *
0x18001989c  mov     rcx, rbx; char *
0x18001989f  call    ?IsTrailByte@@YAHPEBD0@Z; IsTrailByte(char const *,char const *)
0x1800198a4  test    eax, eax
0x1800198a6  jnz     short loc_1800198DA
0x1800198a8  lea     rdx, [rdi-1]; char *
0x1800198ac  cmp     byte ptr [rdx], 5Ch ; '\'
0x1800198af  jnz     short loc_1800198C2
0x1800198b1  cmp     rdx, rbx
0x1800198b4  jz      short loc_1800198DA
0x1800198b6  mov     rcx, rbx; char *
0x1800198b9  call    ?IsTrailByte@@YAHPEBD0@Z; IsTrailByte(char const *,char const *)
0x1800198be  test    eax, eax
0x1800198c0  jz      short loc_1800198DA
0x1800198c2  mov     rcx, rsi; lpString
0x1800198c5  call    cs:__imp_lstrlenA
0x1800198cb  mov     rdx, rsi; Src
0x1800198ce  mov     rcx, rdi; void *
0x1800198d1  lea     r8d, [rax+1]; Size
0x1800198d5  call    memmove_0
0x1800198da  mov     rbx, [rsp+28h+arg_0]
0x1800198df  mov     rsi, [rsp+28h+arg_8]
0x1800198e4  add     rsp, 20h
0x1800198e8  pop     rdi
0x1800198e9  retn
```
