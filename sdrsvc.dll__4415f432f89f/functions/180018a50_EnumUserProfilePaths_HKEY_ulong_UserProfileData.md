# EnumUserProfilePaths(HKEY__ *,ulong *,_UserProfileData * *)

- ea: `0x180018a50`
- end: `0x180018c10`
- name: `?EnumUserProfilePaths@@YAJPEAUHKEY__@@PEAKPEAPEAU_UserProfileData@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int *, struct _UserProfileData **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800106f4`

## callees

- `0x18001586c`
- `0x180015974`
- `0x180018a50`
- `0x1800190bc`
- `0x18002170a`
- `0x180021740`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180018b74`
- `msvcrt!_wcsupr` at `0x180018b74`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180018b40`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180018b40`

## string_xrefs

- `0x180018a85`: `EnumUserProfilePaths`

## pseudocode

```c
__int64 __fastcall EnumUserProfilePaths(HKEY hKey, unsigned int *a2, struct _UserProfileData **a3)
{
  struct _UserProfileData *v6; // rax
  __int64 v7; // rcx
  __int16 v8; // ax
  DWORD v9; // edx
  LSTATUS v10; // eax
  signed int v11; // ebx
  int UserProfileData; // eax
  __int16 v13; // ax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  signed int v16; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v17; // [rsp+4Ch] [rbp-B4h]
  __int16 v18; // [rsp+4Eh] [rbp-B2h]
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "EnumUserProfilePaths", 591, 1);
  memset_0(Name, 0, 0x208u);
  v6 = *a3;
  cchName = 260;
  if ( v6 )
  {
    v7 = 64;
    do
    {
      *(_BYTE *)v6 = 0;
      v6 = (struct _UserProfileData *)((char *)v6 + 1);
      --v7;
    }
    while ( v7 );
  }
  v8 = 599;
  if ( hKey )
  {
    v17 = 599;
    if ( a2 )
    {
      v16 = 0;
      v17 = 601;
      while ( 1 )
      {
        v9 = *a2;
        cchName = 260;
        v10 = RegEnumKeyExW(hKey, v9, Name, &cchName, 0, 0, 0, 0);
        ++*a2;
        v11 = v10;
        if ( v10 == 259 )
          break;
        if ( v10 > 0 )
          v11 = (unsigned __int16)v10 | 0x80070000;
        v16 = v11;
        if ( v11 < 0 )
        {
          v18 = 616;
          goto LABEL_21;
        }
        v17 = 616;
        _wcsupr(Name);
        UserProfileData = GetUserProfileData(hKey, Name, a3);
        v16 = UserProfileData;
        v11 = UserProfileData;
        if ( UserProfileData < 0 )
        {
          v18 = 620;
          goto LABEL_21;
        }
        v17 = 620;
        if ( UserProfileData != 1 )
        {
          v11 = 0;
          v13 = 624;
LABEL_14:
          v17 = v13;
          goto LABEL_20;
        }
      }
      v11 = 1;
      v13 = 614;
      goto LABEL_14;
    }
    v8 = 600;
  }
  v18 = v8;
  v11 = -2147024809;
LABEL_20:
  v16 = v11;
LABEL_21:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180018a50  mov     [rsp-8+arg_18], rbx
0x180018a55  push    rbp
0x180018a56  push    rsi
0x180018a57  push    rdi
0x180018a58  push    r13
0x180018a5a  push    r14
0x180018a5c  lea     rbp, [rsp-1A0h]
0x180018a64  sub     rsp, 2A0h
0x180018a6b  mov     rax, cs:__security_cookie
0x180018a72  xor     rax, rsp
0x180018a75  mov     [rbp+1C0h+var_30], rax
0x180018a7c  mov     r14, r8
0x180018a7f  mov     rdi, rdx
0x180018a82  mov     rsi, rcx
0x180018a85  lea     rdx, aEnumuserprofil; "EnumUserProfilePaths"
0x180018a8c  mov     r8d, 24Fh; unsigned __int16
0x180018a92  lea     rcx, [rsp+2C0h+var_278]; this
0x180018a97  mov     r9d, 1; unsigned __int16
0x180018a9d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180018aa2  xor     edx, edx; Val
0x180018aa4  lea     rcx, [rbp+1C0h+Name]; void *
0x180018aa8  mov     r8d, 208h; Size
0x180018aae  call    memset_0
0x180018ab3  mov     rax, [r14]
0x180018ab6  mov     [rsp+2C0h+cchName], 104h
0x180018abe  test    rax, rax
0x180018ac1  jz      short loc_180018AD4
0x180018ac3  mov     ecx, 40h ; '@'
0x180018ac8  mov     byte ptr [rax], 0
0x180018acb  inc     rax
0x180018ace  sub     rcx, 1
0x180018ad2  jnz     short loc_180018AC8
0x180018ad4  mov     eax, 257h
0x180018ad9  test    rsi, rsi
0x180018adc  jz      loc_180018BD0
0x180018ae2  mov     [rsp+2C0h+var_274], ax
0x180018ae7  test    rdi, rdi
0x180018aea  jz      loc_180018BCB
0x180018af0  mov     eax, 259h
0x180018af5  mov     [rsp+2C0h+var_278], 0
0x180018afd  mov     [rsp+2C0h+var_274], ax
0x180018b02  lea     r13d, [rax+13h]
0x180018b06  mov     edx, [rdi]; dwIndex
0x180018b08  lea     r9, [rsp+2C0h+cchName]; lpcchName
0x180018b0d  mov     [rsp+2C0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180018b16  lea     r8, [rbp+1C0h+Name]; lpName
0x180018b1a  mov     [rsp+2C0h+lpcchClass], 0; lpcchClass
0x180018b23  mov     rcx, rsi; hKey
0x180018b26  mov     [rsp+2C0h+lpClass], 0; lpClass
0x180018b2f  mov     [rsp+2C0h+lpReserved], 0; lpReserved
0x180018b38  mov     [rsp+2C0h+cchName], 104h
0x180018b40  call    cs:__imp_RegEnumKeyExW
0x180018b46  inc     dword ptr [rdi]
0x180018b48  mov     ebx, eax
0x180018b4a  cmp     eax, 103h
0x180018b4f  jz      short loc_180018BBF
0x180018b51  test    eax, eax
0x180018b53  jle     short loc_180018B5E
0x180018b55  movzx   ebx, ax
0x180018b58  or      ebx, 80070000h
0x180018b5e  mov     [rsp+2C0h+var_278], ebx
0x180018b62  mov     eax, 268h
0x180018b67  test    ebx, ebx
0x180018b69  js      short loc_180018BB8
0x180018b6b  lea     rcx, [rbp+1C0h+Name]; String
0x180018b6f  mov     [rsp+2C0h+var_274], ax
0x180018b74  call    cs:__imp__wcsupr
0x180018b7a  mov     r8, r14; struct _UserProfileData **
0x180018b7d  lea     rdx, [rbp+1C0h+Name]; unsigned __int16 *
0x180018b81  mov     rcx, rsi; hKey
0x180018b84  call    ?GetUserProfileData@@YAJQEAUHKEY__@@PEBGPEAPEAU_UserProfileData@@@Z; GetUserProfileData(HKEY__ * const,ushort const *,_UserProfileData * *)
0x180018b89  mov     [rsp+2C0h+var_278], eax
0x180018b8d  mov     ebx, eax
0x180018b8f  test    eax, eax
0x180018b91  js      short loc_180018BB0
0x180018b93  mov     [rsp+2C0h+var_274], r13w
0x180018b99  cmp     eax, 1
0x180018b9c  jz      loc_180018B06
0x180018ba2  xor     ebx, ebx
0x180018ba4  mov     eax, 270h
0x180018ba9  mov     [rsp+2C0h+var_274], ax
0x180018bae  jmp     short loc_180018BDA
0x180018bb0  mov     [rsp+2C0h+var_272], r13w
0x180018bb6  jmp     short loc_180018BDE
0x180018bb8  mov     [rsp+2C0h+var_272], ax
0x180018bbd  jmp     short loc_180018BDE
0x180018bbf  mov     ebx, 1
0x180018bc4  mov     eax, 266h
0x180018bc9  jmp     short loc_180018BA9
0x180018bcb  mov     eax, 258h
0x180018bd0  mov     [rsp+2C0h+var_272], ax
0x180018bd5  mov     ebx, 80070057h
0x180018bda  mov     [rsp+2C0h+var_278], ebx
0x180018bde  lea     rcx, [rsp+2C0h+var_278]; this
0x180018be3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180018be8  mov     eax, ebx
0x180018bea  mov     rcx, [rbp+1C0h+var_30]
0x180018bf1  xor     rcx, rsp; StackCookie
0x180018bf4  call    __security_check_cookie
0x180018bf9  mov     rbx, [rsp+2C0h+arg_18]
0x180018c01  add     rsp, 2A0h
0x180018c08  pop     r14
0x180018c0a  pop     r13
0x180018c0c  pop     rdi
0x180018c0d  pop     rsi
0x180018c0e  pop     rbp
0x180018c0f  retn
```
