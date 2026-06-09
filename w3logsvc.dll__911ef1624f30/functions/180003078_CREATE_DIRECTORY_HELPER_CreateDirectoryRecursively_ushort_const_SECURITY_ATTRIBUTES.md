# CREATE_DIRECTORY_HELPER::CreateDirectoryRecursively(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180003078`
- end: `0x1800031ca`
- name: `?CreateDirectoryRecursively@CREATE_DIRECTORY_HELPER@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180004878`

## callees

- `0x180001edc`
- `0x180003078`
- `0x18000e97a`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000318b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000318b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000309f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180003181`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000309f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180003181`

## pseudocode

```c
__int64 __fastcall CREATE_DIRECTORY_HELPER::CreateDirectoryRecursively(
        const unsigned __int16 *a1,
        struct _SECURITY_ATTRIBUTES *a2)
{
  signed int v2; // ebx
  const unsigned __int16 *v3; // rdi
  signed int LastError; // eax
  __int64 v5; // rcx
  WCHAR *v6; // rax
  __int64 v7; // rdx
  WCHAR *v8; // rcx
  __int16 *v9; // rdi
  __int16 v10; // ax
  signed int v11; // eax
  __int64 v13; // [rsp+20h] [rbp-258h] BYREF
  WCHAR PathName[3]; // [rsp+30h] [rbp-248h] BYREF
  __int16 v15; // [rsp+36h] [rbp-242h] BYREF

  v2 = 0;
  v3 = a1;
  if ( !CreateDirectoryW(a1, 0) )
  {
    v13 = 0;
    memset_0(PathName, 0, 0x208u);
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 == -2147024893 )
    {
      v5 = 2147483646;
      v6 = PathName;
      v7 = 260;
      do
      {
        if ( !v5 )
          break;
        if ( !*v3 )
          break;
        *v6++ = *v3++;
        --v5;
        --v7;
      }
      while ( v7 );
      v8 = v6 - 1;
      if ( v7 )
        v8 = v6;
      *v8 = 0;
      if ( v7 )
      {
        v2 = CREATE_DIRECTORY_HELPER::PathCchAddBackslashEx<260>(PathName, &v13);
        if ( v2 >= 0 )
        {
          if ( v13 )
          {
            v9 = &v15;
            if ( v15 )
            {
              do
              {
                v10 = *v9;
                do
                {
                  if ( v10 == 92 )
                    break;
                  v10 = *++v9;
                }
                while ( *v9 );
                if ( *v9 )
                {
                  *v9 = 0;
                  v2 = 0;
                  if ( !CreateDirectoryW(PathName, 0) )
                  {
                    v11 = GetLastError();
                    v2 = v11;
                    if ( v11 > 0 )
                      v2 = (unsigned __int16)v11 | 0x80070000;
                  }
                }
                *v9++ = 92;
              }
              while ( *v9 );
            }
          }
        }
      }
      else
      {
        return (unsigned int)-2147024690;
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003078  push    rbx
0x18000307a  push    rbp
0x18000307b  push    rsi
0x18000307c  push    rdi
0x18000307d  sub     rsp, 258h
0x180003084  mov     rax, cs:__security_cookie
0x18000308b  xor     rax, rsp
0x18000308e  mov     [rsp+278h+var_38], rax
0x180003096  xor     esi, esi
0x180003098  xor     edx, edx; lpSecurityAttributes
0x18000309a  mov     ebx, esi
0x18000309c  mov     rdi, rcx
0x18000309f  call    cs:__imp_CreateDirectoryW
0x1800030a5  test    eax, eax
0x1800030a7  jnz     loc_1800031AC
0x1800030ad  xor     edx, edx; Val
0x1800030af  mov     [rsp+278h+var_258], rsi
0x1800030b4  mov     r8d, 208h; Size
0x1800030ba  lea     rcx, [rsp+278h+PathName]; void *
0x1800030bf  call    memset_0
0x1800030c4  call    cs:__imp_GetLastError
0x1800030ca  mov     ebx, eax
0x1800030cc  test    eax, eax
0x1800030ce  jle     short loc_1800030D9
0x1800030d0  movzx   ebx, ax
0x1800030d3  or      ebx, 80070000h
0x1800030d9  cmp     ebx, 80070003h
0x1800030df  jnz     loc_1800031AC
0x1800030e5  mov     ecx, 7FFFFFFEh
0x1800030ea  lea     rax, [rsp+278h+PathName]
0x1800030ef  mov     edx, 104h
0x1800030f4  test    rcx, rcx
0x1800030f7  jz      short loc_180003118
0x1800030f9  movzx   r8d, word ptr [rdi]
0x1800030fd  test    r8w, r8w
0x180003101  jz      short loc_180003118
0x180003103  mov     [rax], r8w
0x180003107  add     rdi, 2
0x18000310b  add     rax, 2
0x18000310f  dec     rcx
0x180003112  sub     rdx, 1
0x180003116  jnz     short loc_1800030F4
0x180003118  test    rdx, rdx
0x18000311b  lea     rcx, [rax-2]
0x18000311f  cmovnz  rcx, rax
0x180003123  mov     [rcx], si
0x180003126  jnz     short loc_18000312F
0x180003128  mov     ebx, 800700CEh
0x18000312d  jmp     short loc_1800031AC
0x18000312f  lea     rdx, [rsp+278h+var_258]
0x180003134  lea     rcx, [rsp+278h+PathName]
0x180003139  call    ??$PathCchAddBackslashEx@$0BAE@@CREATE_DIRECTORY_HELPER@@CAJAEAY0BAE@GPEAPEAG@Z; CREATE_DIRECTORY_HELPER::PathCchAddBackslashEx<260>(ushort (&)[260],ushort * *)
0x18000313e  mov     ebx, eax
0x180003140  test    eax, eax
0x180003142  js      short loc_1800031AC
0x180003144  cmp     [rsp+278h+var_258], rsi
0x180003149  jz      short loc_1800031AC
0x18000314b  lea     rdi, [rsp+278h+var_242]
0x180003150  cmp     [rsp+278h+var_242], si
0x180003155  jz      short loc_1800031AC
0x180003157  mov     ebp, 5Ch ; '\'
0x18000315c  movzx   eax, word ptr [rdi]
0x18000315f  cmp     ax, bp
0x180003162  jz      short loc_180003170
0x180003164  add     rdi, 2
0x180003168  movzx   eax, word ptr [rdi]
0x18000316b  test    ax, ax
0x18000316e  jnz     short loc_18000315F
0x180003170  cmp     [rdi], si
0x180003173  jz      short loc_1800031A0
0x180003175  xor     edx, edx; lpSecurityAttributes
0x180003177  mov     [rdi], si
0x18000317a  lea     rcx, [rsp+278h+PathName]; lpPathName
0x18000317f  mov     ebx, esi
0x180003181  call    cs:__imp_CreateDirectoryW
0x180003187  test    eax, eax
0x180003189  jnz     short loc_1800031A0
0x18000318b  call    cs:__imp_GetLastError
0x180003191  mov     ebx, eax
0x180003193  test    eax, eax
0x180003195  jle     short loc_1800031A0
0x180003197  movzx   ebx, ax
0x18000319a  or      ebx, 80070000h
0x1800031a0  mov     [rdi], bp
0x1800031a3  add     rdi, 2
0x1800031a7  cmp     [rdi], si
0x1800031aa  jnz     short loc_18000315C
0x1800031ac  mov     eax, ebx
0x1800031ae  mov     rcx, [rsp+278h+var_38]
0x1800031b6  xor     rcx, rsp; StackCookie
0x1800031b9  call    __security_check_cookie
0x1800031be  add     rsp, 258h
0x1800031c5  pop     rdi
0x1800031c6  pop     rsi
0x1800031c7  pop     rbp
0x1800031c8  pop     rbx
0x1800031c9  retn
```
