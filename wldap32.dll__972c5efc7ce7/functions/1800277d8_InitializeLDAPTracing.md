# InitializeLDAPTracing

- ea: `0x1800277d8`
- end: `0x180027a25`
- name: `InitializeLDAPTracing`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180024df0`

## callees

- `0x1800277d8`
- `0x180034510`
- `0x180034e6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180027845`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180027845`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002781f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002781f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279f6`
- `ntdll!EtwEventRegister` at `0x1800279b6`
- `ntdll!EtwEventRegister` at `0x1800279b6`
- `ntdll!EtwEventUnregister` at `0x180027a10`
- `ntdll!EtwEventUnregister` at `0x180027a10`

## string_xrefs

- `0x180027871`: `SYSTEM\CurrentControlSet\Services\ldap\Tracing`

## pseudocode

```c
WCHAR *InitializeLDAPTracing()
{
  DWORD ModuleFileNameW; // eax
  wchar_t *v1; // rax
  WCHAR *v2; // rdx
  __int64 v3; // r11
  __int64 v4; // rcx
  __int64 v5; // r9
  WCHAR *result; // rax
  __int64 v7; // r8
  WCHAR *v8; // rcx
  WCHAR *v9; // rax
  const wchar_t *v10; // r10
  __int64 v11; // rcx
  WCHAR *v12; // rcx
  WCHAR *v13; // rax
  __int64 v14; // rbx
  WCHAR *v15; // rcx
  WCHAR Filename[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(Filename, 0, 0x208u);
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( !ModuleFileNameW || ModuleFileNameW == 260 )
  {
    GetLastError();
    goto LABEL_34;
  }
  v1 = wcsrchr(Filename, 0x5Cu);
  if ( v1 )
    v2 = v1 + 1;
  else
    v2 = Filename;
  v3 = 2147483646;
  v4 = 2147483646;
  v5 = (__int64)L"SYSTEM\\CurrentControlSet\\Services\\ldap\\Tracing";
  result = &g_pszProcessKeyName;
  v7 = 520;
  do
  {
    if ( !v4 )
      break;
    if ( !*(_WORD *)v5 )
      break;
    *result = *(_WORD *)v5;
    v5 += 2;
    ++result;
    --v4;
    --v7;
  }
  while ( v7 );
  v8 = result - 1;
  if ( v7 )
    v8 = result;
  *v8 = 0;
  if ( v7 )
  {
    v7 = 520;
    v9 = &g_pszProcessKeyName;
    do
    {
      if ( !*v9 )
        break;
      ++v9;
      --v7;
    }
    while ( v7 );
    result = (WCHAR *)-v7;
    v5 = (520 - v7) & -(__int64)(v7 != 0);
    if ( v7 )
    {
      v10 = L"\\";
      result = &g_pszProcessKeyName + v5;
      v11 = 2147483646;
      v7 = 520 - v5;
      if ( v5 != 520 )
      {
        do
        {
          if ( !v11 )
            break;
          v5 = *v10;
          if ( !(_WORD)v5 )
            break;
          *result = v5;
          ++v10;
          ++result;
          --v11;
          --v7;
        }
        while ( v7 );
      }
      v12 = result - 1;
      if ( v7 )
        v12 = result;
      *v12 = 0;
      if ( v7 )
      {
        v7 = 520;
        v13 = &g_pszProcessKeyName;
        do
        {
          if ( !*v13 )
            break;
          ++v13;
          --v7;
        }
        while ( v7 );
        result = (WCHAR *)-v7;
        v5 = (520 - v7) & -(__int64)(v7 != 0);
        if ( v7 )
        {
          result = &g_pszProcessKeyName + v5;
          v14 = 520 - v5;
          if ( 520 != v5 )
          {
            do
            {
              if ( !v3 )
                break;
              if ( !*v2 )
                break;
              *result++ = *v2++;
              --v3;
              --v14;
            }
            while ( v14 );
          }
          v15 = result - 1;
          if ( v14 )
            v15 = result;
          *v15 = 0;
          if ( v14 )
          {
LABEL_34:
            result = (WCHAR *)EtwEventRegister(LDAP_CLIENT_PUBLISHER, ControlCallback, 0, &g_RegistrationHandle);
            if ( !(_DWORD)result )
              return result;
          }
        }
      }
    }
  }
  if ( g_RegistrationHandle )
  {
    result = (WCHAR *)EtwEventUnregister(g_RegistrationHandle, v2, v7, v5);
    g_RegistrationHandle = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800277d8  mov     [rsp+arg_0], rbx
0x1800277dd  mov     [rsp+arg_8], rsi
0x1800277e2  push    rdi
0x1800277e3  sub     rsp, 240h
0x1800277ea  mov     rax, cs:__security_cookie
0x1800277f1  xor     rax, rsp
0x1800277f4  mov     [rsp+248h+var_18], rax
0x1800277fc  mov     ebx, 208h
0x180027801  lea     rcx, [rsp+248h+Filename]; void *
0x180027806  mov     r8d, ebx; Size
0x180027809  xor     edx, edx; Val
0x18002780b  call    memset_0
0x180027810  mov     esi, 104h
0x180027815  lea     rdx, [rsp+248h+Filename]; lpFilename
0x18002781a  mov     r8d, esi; nSize
0x18002781d  xor     ecx, ecx; hModule
0x18002781f  call    cs:__imp_GetModuleFileNameW
0x180027826  nop     dword ptr [rax+rax+00h]
0x18002782b  xor     edi, edi
0x18002782d  test    eax, eax
0x18002782f  jz      loc_1800279F6
0x180027835  cmp     eax, esi
0x180027837  jz      loc_1800279F6
0x18002783d  lea     edx, [rdi+5Ch]; Ch
0x180027840  lea     rcx, [rsp+248h+Filename]; Str
0x180027845  call    cs:__imp_wcsrchr
0x18002784c  nop     dword ptr [rax+rax+00h]
0x180027851  mov     rdx, rax
0x180027854  test    rax, rax
0x180027857  jz      loc_1800279EC
0x18002785d  add     rdx, 2
0x180027861  mov     r11d, 7FFFFFFEh
0x180027867  lea     rsi, ?g_pszProcessKeyName@@3PAGA; ushort near * g_pszProcessKeyName
0x18002786e  mov     ecx, r11d
0x180027871  lea     r9, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\ld"...
0x180027878  mov     rax, rsi
0x18002787b  mov     r8, rbx
0x18002787e  test    rcx, rcx
0x180027881  jz      short loc_1800278A2
0x180027883  movzx   r10d, word ptr [r9]
0x180027887  test    r10w, r10w
0x18002788b  jz      short loc_1800278A2
0x18002788d  mov     [rax], r10w
0x180027891  add     r9, 2
0x180027895  add     rax, 2
0x180027899  dec     rcx
0x18002789c  sub     r8, 1
0x1800278a0  jnz     short loc_18002787E
0x1800278a2  test    r8, r8
0x1800278a5  lea     rcx, [rax-2]
0x1800278a9  cmovnz  rcx, rax
0x1800278ad  mov     [rcx], di
0x1800278b0  jz      loc_180027A04
0x1800278b6  mov     r8, rbx
0x1800278b9  mov     rax, rsi
0x1800278bc  cmp     [rax], di
0x1800278bf  jz      short loc_1800278CB
0x1800278c1  add     rax, 2
0x1800278c5  sub     r8, 1
0x1800278c9  jnz     short loc_1800278BC
0x1800278cb  mov     rcx, rbx
0x1800278ce  mov     rax, r8
0x1800278d1  sub     rcx, r8
0x1800278d4  neg     rax
0x1800278d7  sbb     r9, r9
0x1800278da  and     r9, rcx
0x1800278dd  test    r8, r8
0x1800278e0  jz      loc_180027A04
0x1800278e6  mov     r8, rbx
0x1800278e9  lea     r10, asc_18004F0F4; "\\"
0x1800278f0  lea     rax, [rsi+r9*2]
0x1800278f4  mov     rcx, r11
0x1800278f7  sub     r8, r9
0x1800278fa  jz      short loc_180027920
0x1800278fc  test    rcx, rcx
0x1800278ff  jz      short loc_180027920
0x180027901  movzx   r9d, word ptr [r10]
0x180027905  test    r9w, r9w
0x180027909  jz      short loc_180027920
0x18002790b  mov     [rax], r9w
0x18002790f  add     r10, 2
0x180027913  add     rax, 2
0x180027917  dec     rcx
0x18002791a  sub     r8, 1
0x18002791e  jnz     short loc_1800278FC
0x180027920  test    r8, r8
0x180027923  lea     rcx, [rax-2]
0x180027927  cmovnz  rcx, rax
0x18002792b  mov     [rcx], di
0x18002792e  jz      loc_180027A04
0x180027934  mov     r8, rbx
0x180027937  mov     rax, rsi
0x18002793a  cmp     [rax], di
0x18002793d  jz      short loc_180027949
0x18002793f  add     rax, 2
0x180027943  sub     r8, 1
0x180027947  jnz     short loc_18002793A
0x180027949  mov     rcx, rbx
0x18002794c  mov     rax, r8
0x18002794f  sub     rcx, r8
0x180027952  neg     rax
0x180027955  sbb     r9, r9
0x180027958  and     r9, rcx
0x18002795b  test    r8, r8
0x18002795e  jz      loc_180027A04
0x180027964  lea     rax, [rsi+r9*2]
0x180027968  sub     rbx, r9
0x18002796b  jz      short loc_18002798E
0x18002796d  test    r11, r11
0x180027970  jz      short loc_18002798E
0x180027972  movzx   ecx, word ptr [rdx]
0x180027975  test    cx, cx
0x180027978  jz      short loc_18002798E
0x18002797a  mov     [rax], cx
0x18002797d  add     rdx, 2
0x180027981  add     rax, 2
0x180027985  dec     r11
0x180027988  sub     rbx, 1
0x18002798c  jnz     short loc_18002796D
0x18002798e  test    rbx, rbx
0x180027991  lea     rcx, [rax-2]
0x180027995  cmovnz  rcx, rax
0x180027999  mov     [rcx], di
0x18002799c  jz      short loc_180027A04
0x18002799e  lea     r9, ?g_RegistrationHandle@@3_KA; unsigned __int64 g_RegistrationHandle
0x1800279a5  xor     r8d, r8d
0x1800279a8  lea     rdx, ControlCallback
0x1800279af  lea     rcx, LDAP_CLIENT_PUBLISHER
0x1800279b6  call    cs:__imp_EtwEventRegister
0x1800279bd  nop     dword ptr [rax+rax+00h]
0x1800279c2  test    eax, eax
0x1800279c4  jnz     short loc_180027A04
0x1800279c6  mov     rcx, [rsp+248h+var_18]
0x1800279ce  xor     rcx, rsp; StackCookie
0x1800279d1  call    __security_check_cookie
0x1800279d6  lea     r11, [rsp+248h+var_8]
0x1800279de  mov     rbx, [r11+10h]
0x1800279e2  mov     rsi, [r11+18h]
0x1800279e6  mov     rsp, r11
0x1800279e9  pop     rdi
0x1800279ea  retn
0x1800279ec  lea     rdx, [rsp+248h+Filename]
0x1800279f1  jmp     loc_180027861
0x1800279f6  call    cs:__imp_GetLastError
0x1800279fd  nop     dword ptr [rax+rax+00h]
0x180027a02  jmp     short loc_18002799E
0x180027a04  mov     rcx, cs:?g_RegistrationHandle@@3_KA; unsigned __int64 g_RegistrationHandle
0x180027a0b  test    rcx, rcx
0x180027a0e  jz      short loc_1800279C6
0x180027a10  call    cs:__imp_EtwEventUnregister
0x180027a17  nop     dword ptr [rax+rax+00h]
0x180027a1c  mov     cs:?g_RegistrationHandle@@3_KA, rdi; unsigned __int64 g_RegistrationHandle
0x180027a23  jmp     short loc_1800279C6
```
