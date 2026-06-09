# GetLdapProcessRegistryKeyPath(ushort *,ushort *,unsigned __int64)

- ea: `0x180026490`
- end: `0x18002669f`
- name: `?GetLdapProcessRegistryKeyPath@@YAJPEAG0_K@Z`
- size: `527`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180024df0`

## callees

- `0x180026490`
- `0x180034510`
- `0x180034e6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002650d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002650d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800264dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800264dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002668c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002668c`

## pseudocode

```c
__int64 __fastcall GetLdapProcessRegistryKeyPath(unsigned __int16 *a1, unsigned __int16 *a2)
{
  DWORD ModuleFileNameW; // eax
  wchar_t *v5; // rax
  WCHAR *v6; // r10
  __int64 v7; // r11
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned __int16 *v10; // r8
  unsigned __int16 *v11; // rax
  unsigned int v12; // edi
  unsigned int v13; // ecx
  __int64 result; // rax
  __int64 v15; // rcx
  unsigned __int16 *i; // rax
  unsigned int v17; // edx
  const wchar_t *v18; // r8
  __int64 v19; // rdx
  unsigned __int16 *v20; // r9
  unsigned __int16 *v21; // rax
  __int64 v22; // rdx
  unsigned __int16 *j; // rax
  unsigned __int16 *v24; // r8
  unsigned __int16 *v25; // rcx
  WCHAR Filename[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(Filename, 0, 0x208u);
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( !ModuleFileNameW || ModuleFileNameW == 260 )
  {
    GetLastError();
    return 0;
  }
  else
  {
    v5 = wcsrchr(Filename, 0x5Cu);
    if ( v5 )
      v6 = v5 + 1;
    else
      v6 = Filename;
    v7 = 2147483646;
    v8 = 520;
    v9 = 2147483646;
    v10 = a2;
    do
    {
      if ( !v9 )
        break;
      if ( !*a1 )
        break;
      *v10++ = *a1++;
      --v9;
      --v8;
    }
    while ( v8 );
    v11 = v10 - 1;
    v12 = -2147024774;
    v13 = -2147024774;
    if ( v8 )
    {
      v11 = v10;
      v13 = 0;
    }
    *v11 = 0;
    if ( v8 )
    {
      v15 = 520;
      for ( i = a2; *i; ++i )
      {
        if ( !--v15 )
          return (unsigned int)-2147024809;
      }
      v18 = L"\\";
      v19 = 2147483646;
      v20 = &a2[520 - v15];
      do
      {
        if ( !v19 )
          break;
        if ( !*v18 )
          break;
        *v20++ = *v18++;
        --v19;
        --v15;
      }
      while ( v15 );
      v21 = v20 - 1;
      v17 = -2147024774;
      if ( v15 )
      {
        v21 = v20;
        v17 = 0;
      }
      *v21 = 0;
      if ( !v15 )
        return v17;
      v22 = 520;
      for ( j = a2; *j; ++j )
      {
        if ( !--v22 )
          return 2147942487LL;
      }
      v24 = &a2[520 - v22];
      do
      {
        if ( !v7 )
          break;
        if ( !*v6 )
          break;
        *v24++ = *v6++;
        --v7;
        --v22;
      }
      while ( v22 );
      v25 = v24 - 1;
      if ( v22 )
      {
        v25 = v24;
        v12 = 0;
      }
      result = v12;
      *v25 = 0;
    }
    else
    {
      return v13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180026490  mov     [rsp+arg_10], rbx
0x180026495  mov     [rsp+arg_18], rsi
0x18002649a  push    r14
0x18002649c  sub     rsp, 240h
0x1800264a3  mov     rax, cs:__security_cookie
0x1800264aa  xor     rax, rsp
0x1800264ad  mov     [rsp+248h+var_18], rax
0x1800264b5  mov     r14, rdx
0x1800264b8  mov     rbx, rcx
0x1800264bb  mov     esi, 208h
0x1800264c0  lea     rcx, [rsp+248h+Filename]; void *
0x1800264c5  mov     r8d, esi; Size
0x1800264c8  xor     edx, edx; Val
0x1800264ca  call    memset_0
0x1800264cf  mov     r8d, 104h; nSize
0x1800264d5  lea     rdx, [rsp+248h+Filename]; lpFilename
0x1800264da  xor     ecx, ecx; hModule
0x1800264dc  call    cs:__imp_GetModuleFileNameW
0x1800264e3  nop     dword ptr [rax+rax+00h]
0x1800264e8  test    eax, eax
0x1800264ea  jz      loc_18002668A
0x1800264f0  cmp     eax, 104h
0x1800264f5  jz      loc_18002668A
0x1800264fb  mov     edx, 5Ch ; '\'; Ch
0x180026500  mov     [rsp+248h+arg_0], rdi
0x180026508  lea     rcx, [rsp+248h+Filename]; Str
0x18002650d  call    cs:__imp_wcsrchr
0x180026514  nop     dword ptr [rax+rax+00h]
0x180026519  mov     r10, rax
0x18002651c  test    rax, rax
0x18002651f  jz      loc_180026680
0x180026525  add     r10, 2
0x180026529  mov     r11d, 7FFFFFFEh
0x18002652f  mov     rdx, rsi
0x180026532  mov     ecx, r11d
0x180026535  mov     r8, r14
0x180026538  test    rcx, rcx
0x18002653b  jz      short loc_18002655A
0x18002653d  movzx   eax, word ptr [rbx]
0x180026540  test    ax, ax
0x180026543  jz      short loc_18002655A
0x180026545  mov     [r8], ax
0x180026549  add     rbx, 2
0x18002654d  add     r8, 2
0x180026551  dec     rcx
0x180026554  sub     rdx, 1
0x180026558  jnz     short loc_180026538
0x18002655a  xor     ebx, ebx
0x18002655c  lea     rax, [r8-2]
0x180026560  test    rdx, rdx
0x180026563  mov     edi, 8007007Ah
0x180026568  mov     ecx, edi
0x18002656a  cmovnz  rax, r8
0x18002656e  cmovnz  ecx, ebx
0x180026571  mov     [rax], bx
0x180026574  jnz     short loc_1800265A7
0x180026576  mov     eax, ecx
0x180026578  mov     rdi, [rsp+248h+arg_0]
0x180026580  mov     rcx, [rsp+248h+var_18]
0x180026588  xor     rcx, rsp; StackCookie
0x18002658b  call    __security_check_cookie
0x180026590  lea     r11, [rsp+248h+var_8]
0x180026598  mov     rbx, [r11+20h]
0x18002659c  mov     rsi, [r11+28h]
0x1800265a0  mov     rsp, r11
0x1800265a3  pop     r14
0x1800265a5  retn
0x1800265a7  mov     rcx, rsi
0x1800265aa  mov     rax, r14
0x1800265ad  nop     dword ptr [rax]
0x1800265b0  cmp     [rax], bx
0x1800265b3  jz      short loc_1800265C8
0x1800265b5  add     rax, 2
0x1800265b9  sub     rcx, 1
0x1800265bd  jnz     short loc_1800265B0
0x1800265bf  mov     edx, 80070057h
0x1800265c4  mov     eax, edx
0x1800265c6  jmp     short loc_180026578
0x1800265c8  mov     rax, rsi
0x1800265cb  lea     r8, asc_18004F0F4; "\\"
0x1800265d2  sub     rax, rcx
0x1800265d5  mov     rdx, r11
0x1800265d8  lea     r9, [r14+rax*2]
0x1800265dc  test    rcx, rcx
0x1800265df  jz      short loc_180026604
0x1800265e1  test    rdx, rdx
0x1800265e4  jz      short loc_180026604
0x1800265e6  movzx   eax, word ptr [r8]
0x1800265ea  test    ax, ax
0x1800265ed  jz      short loc_180026604
0x1800265ef  mov     [r9], ax
0x1800265f3  add     r8, 2
0x1800265f7  add     r9, 2
0x1800265fb  dec     rdx
0x1800265fe  sub     rcx, 1
0x180026602  jnz     short loc_1800265E1
0x180026604  test    rcx, rcx
0x180026607  lea     rax, [r9-2]
0x18002660b  mov     edx, edi
0x18002660d  cmovnz  rax, r9
0x180026611  cmovnz  edx, ebx
0x180026614  mov     [rax], bx
0x180026617  jz      short loc_1800265C4
0x180026619  mov     rdx, rsi
0x18002661c  mov     rax, r14
0x18002661f  nop
0x180026620  cmp     [rax], bx
0x180026623  jz      short loc_180026639
0x180026625  add     rax, 2
0x180026629  sub     rdx, 1
0x18002662d  jnz     short loc_180026620
0x18002662f  mov     eax, 80070057h
0x180026634  jmp     loc_180026578
0x180026639  sub     rsi, rdx
0x18002663c  lea     r8, [r14+rsi*2]
0x180026640  test    rdx, rdx
0x180026643  jz      short loc_180026668
0x180026645  test    r11, r11
0x180026648  jz      short loc_180026668
0x18002664a  movzx   eax, word ptr [r10]
0x18002664e  test    ax, ax
0x180026651  jz      short loc_180026668
0x180026653  mov     [r8], ax
0x180026657  add     r10, 2
0x18002665b  add     r8, 2
0x18002665f  dec     r11
0x180026662  sub     rdx, 1
0x180026666  jnz     short loc_180026645
0x180026668  test    rdx, rdx
0x18002666b  lea     rcx, [r8-2]
0x18002666f  cmovnz  rcx, r8
0x180026673  cmovnz  edi, ebx
0x180026676  mov     eax, edi
0x180026678  mov     [rcx], bx
0x18002667b  jmp     loc_180026578
0x180026680  lea     r10, [rsp+248h+Filename]
0x180026685  jmp     loc_180026529
0x18002668a  xor     ebx, ebx
0x18002668c  call    cs:__imp_GetLastError
0x180026693  nop     dword ptr [rax+rax+00h]
0x180026698  mov     eax, ebx
0x18002669a  jmp     loc_180026580
```
