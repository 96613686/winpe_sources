# QuickCheckUwfFeatureState(bool *)

- ea: `0x180010d10`
- end: `0x180010ec0`
- name: `?QuickCheckUwfFeatureState@@YAJPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x18000f364`

## callees

- `0x18000d5f0`
- `0x18000de30`
- `0x180010d10`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e66`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180010e5b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180010e5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180010d8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180010d8c`

## string_xrefs

- `0x180010d30`: `SYSTEM\CurrentControlSet\Services\uwfvol`

## pseudocode

```c
__int64 __fastcall QuickCheckUwfFeatureState(bool *a1)
{
  int v2; // eax
  signed int v3; // ebx
  signed int LastError; // eax
  __int64 v5; // rdx
  WCHAR *v6; // rax
  __int64 v7; // r8
  __int64 v8; // rcx
  WCHAR *v9; // rax
  const wchar_t *v10; // rdx
  __int64 v11; // rdi
  WCHAR *v12; // rcx
  signed int v13; // eax
  HKEY phkResult[2]; // [rsp+20h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-248h] BYREF

  *a1 = 0;
  phkResult[0] = 0;
  v2 = CUwfRegKey::Open(phkResult, HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\uwfvol", 0x20019u);
  v3 = v2;
  if ( v2 != -2147024894 )
  {
    if ( v2 < 0 )
      goto LABEL_24;
    memset_0(Buffer, 0, 0x208u);
    if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 < 0 )
        goto LABEL_24;
    }
    v5 = 260;
    v6 = Buffer;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v3 = v5 == 0 ? 0x80070057 : 0;
    v7 = (260 - v5) & -(__int64)(v5 != 0);
    if ( !v5 )
      goto LABEL_24;
    v8 = 2147483646;
    v9 = &Buffer[v7];
    v10 = L"\\drivers\\uwfvol.sys";
    v11 = 260 - v7;
    if ( 260 != v7 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*v10 )
          break;
        *v9++ = *v10++;
        --v8;
        --v11;
      }
      while ( v11 );
    }
    v12 = v9 - 1;
    if ( v11 )
      v12 = v9;
    *v12 = 0;
    v3 = v11 == 0 ? 0x8007007A : 0;
    if ( !v11 )
      goto LABEL_24;
    if ( GetFileAttributesW(Buffer) != -1 )
    {
LABEL_23:
      *a1 = 1;
LABEL_24:
      CUwfRegKey::Close(phkResult);
      return (unsigned int)v3;
    }
    v13 = GetLastError();
    v3 = v13;
    if ( v13 != 2 )
    {
      if ( v13 > 0 )
        v3 = (unsigned __int16)v13 | 0x80070000;
      if ( v3 < 0 )
        goto LABEL_24;
      goto LABEL_23;
    }
  }
  *a1 = 0;
  CUwfRegKey::Close(phkResult);
  return 0;
}

```

## disassembly

```asm
0x180010d10  push    rbx
0x180010d12  push    rbp
0x180010d13  push    rsi
0x180010d14  push    rdi
0x180010d15  sub     rsp, 258h
0x180010d1c  mov     rax, cs:__security_cookie
0x180010d23  xor     rax, rsp
0x180010d26  mov     [rsp+278h+var_38], rax
0x180010d2e  xor     ebp, ebp
0x180010d30  lea     r8, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\uw"...
0x180010d37  mov     [rcx], bpl
0x180010d3a  mov     rsi, rcx
0x180010d3d  lea     rcx, [rsp+278h+phkResult]; phkResult
0x180010d42  mov     [rsp+278h+phkResult], rbp
0x180010d47  mov     r9d, 20019h; samDesired
0x180010d4d  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180010d54  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180010d59  mov     ebx, eax
0x180010d5b  cmp     eax, 80070002h
0x180010d60  jz      loc_180010E95
0x180010d66  test    eax, eax
0x180010d68  js      loc_180010E87
0x180010d6e  xor     edx, edx; Val
0x180010d70  lea     rcx, [rsp+278h+Buffer]; void *
0x180010d75  mov     r8d, 208h; Size
0x180010d7b  call    memset_0
0x180010d80  mov     edi, 104h
0x180010d85  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x180010d8a  mov     edx, edi; uSize
0x180010d8c  call    cs:__imp_GetSystemDirectoryW
0x180010d92  test    eax, eax
0x180010d94  jnz     short loc_180010DB3
0x180010d96  call    cs:__imp_GetLastError
0x180010d9c  mov     ebx, eax
0x180010d9e  test    eax, eax
0x180010da0  jle     short loc_180010DAB
0x180010da2  movzx   ebx, ax
0x180010da5  or      ebx, 80070000h
0x180010dab  test    ebx, ebx
0x180010dad  js      loc_180010E87
0x180010db3  mov     rdx, rdi
0x180010db6  lea     rax, [rsp+278h+Buffer]
0x180010dbb  cmp     [rax], bp
0x180010dbe  jz      short loc_180010DCA
0x180010dc0  add     rax, 2
0x180010dc4  sub     rdx, 1
0x180010dc8  jnz     short loc_180010DBB
0x180010dca  mov     rax, rdx
0x180010dcd  mov     rcx, rdi
0x180010dd0  neg     rax
0x180010dd3  mov     rax, rdx
0x180010dd6  sbb     ebx, ebx
0x180010dd8  sub     rcx, rdx
0x180010ddb  not     ebx
0x180010ddd  and     ebx, 80070057h
0x180010de3  neg     rax
0x180010de6  sbb     r8, r8
0x180010de9  and     r8, rcx
0x180010dec  test    rdx, rdx
0x180010def  jz      loc_180010E87
0x180010df5  lea     rax, [rsp+278h+Buffer]
0x180010dfa  mov     ecx, 7FFFFFFEh
0x180010dff  lea     rax, [rax+r8*2]
0x180010e03  lea     rdx, aDriversUwfvolS; "\\drivers\\uwfvol.sys"
0x180010e0a  sub     rdi, r8
0x180010e0d  jz      short loc_180010E33
0x180010e0f  test    rcx, rcx
0x180010e12  jz      short loc_180010E33
0x180010e14  movzx   r8d, word ptr [rdx]
0x180010e18  test    r8w, r8w
0x180010e1c  jz      short loc_180010E33
0x180010e1e  mov     [rax], r8w
0x180010e22  add     rdx, 2
0x180010e26  add     rax, 2
0x180010e2a  dec     rcx
0x180010e2d  sub     rdi, 1
0x180010e31  jnz     short loc_180010E0F
0x180010e33  test    rdi, rdi
0x180010e36  lea     rcx, [rax-2]
0x180010e3a  cmovnz  rcx, rax
0x180010e3e  mov     rax, rdi
0x180010e41  neg     rax
0x180010e44  sbb     ebx, ebx
0x180010e46  not     ebx
0x180010e48  mov     [rcx], bp
0x180010e4b  and     ebx, 8007007Ah
0x180010e51  test    rdi, rdi
0x180010e54  jz      short loc_180010E87
0x180010e56  lea     rcx, [rsp+278h+Buffer]; lpFileName
0x180010e5b  call    cs:__imp_GetFileAttributesW
0x180010e61  cmp     eax, 0FFFFFFFFh
0x180010e64  jnz     short loc_180010E84
0x180010e66  call    cs:__imp_GetLastError
0x180010e6c  mov     ebx, eax
0x180010e6e  cmp     eax, 2
0x180010e71  jz      short loc_180010E95
0x180010e73  test    eax, eax
0x180010e75  jle     short loc_180010E80
0x180010e77  movzx   ebx, ax
0x180010e7a  or      ebx, 80070000h
0x180010e80  test    ebx, ebx
0x180010e82  js      short loc_180010E87
0x180010e84  mov     byte ptr [rsi], 1
0x180010e87  lea     rcx, [rsp+278h+phkResult]; this
0x180010e8c  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180010e91  mov     eax, ebx
0x180010e93  jmp     short loc_180010EA4
0x180010e95  lea     rcx, [rsp+278h+phkResult]; this
0x180010e9a  mov     [rsi], bpl
0x180010e9d  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180010ea2  xor     eax, eax
0x180010ea4  mov     rcx, [rsp+278h+var_38]
0x180010eac  xor     rcx, rsp; StackCookie
0x180010eaf  call    __security_check_cookie
0x180010eb4  add     rsp, 258h
0x180010ebb  pop     rdi
0x180010ebc  pop     rsi
0x180010ebd  pop     rbp
0x180010ebe  pop     rbx
0x180010ebf  retn
```
