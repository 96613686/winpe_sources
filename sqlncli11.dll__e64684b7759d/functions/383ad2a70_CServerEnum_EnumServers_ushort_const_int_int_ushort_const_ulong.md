# CServerEnum::EnumServers(ushort const *,int,int,ushort const *,ulong)

- ea: `0x383ad2a70`
- end: `0x383ad3062`
- name: `?EnumServers@CServerEnum@@AEAAJPEBGHH0K@Z`
- size: `1522`
- prototype: `int(CServerEnum *__hidden this, const unsigned __int16 *, int, int, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x383a2c510`
- `0x383aca9a0`

## callees

- `0x3838427d0`
- `0x3838434c0`
- `0x3838435e0`
- `0x383893160`
- `0x38391aed0`
- `0x38391afe0`
- `0x383a97c74`
- `0x383ad2a70`
- `0x383adaf60`
- `0x383adb360`
- `0x383adb5f0`

## import_xrefs

- `MSVCR100!qsort` at `0x383ad2f62`
- `MSVCR100!qsort` at `0x383ad2f62`
- `MSVCR100!_wcsnicmp` at `0x383ad2e42`
- `MSVCR100!_wcsnicmp` at `0x383ad2e42`
- `MSVCR100!_wcsicmp` at `0x383ad2b80`
- `MSVCR100!_wcsicmp` at `0x383ad2b94`
- `MSVCR100!_wcsicmp` at `0x383ad2ba8`
- `MSVCR100!_wcsicmp` at `0x383ad2bbc`
- `MSVCR100!_wcsicmp` at `0x383ad2b80`
- `MSVCR100!_wcsicmp` at `0x383ad2b94`
- `MSVCR100!_wcsicmp` at `0x383ad2ba8`
- `MSVCR100!_wcsicmp` at `0x383ad2bbc`
- `KERNEL32!GetLastError` at `0x383ad2d6b`
- `KERNEL32!GetLastError` at `0x383ad2d6b`
- `KERNEL32!GetComputerNameW` at `0x383ad2d61`
- `KERNEL32!GetComputerNameW` at `0x383ad2d61`
- `KERNEL32!GetTickCount` at `0x383ad2acf`
- `KERNEL32!GetTickCount` at `0x383ad2c28`
- `KERNEL32!GetTickCount` at `0x383ad2acf`
- `KERNEL32!GetTickCount` at `0x383ad2c28`
- `ADVAPI32!RegOpenKeyExW` at `0x383ad2b23`
- `ADVAPI32!RegOpenKeyExW` at `0x383ad2b23`
- `ADVAPI32!RegEnumValueW` at `0x383ad2b65`
- `ADVAPI32!RegEnumValueW` at `0x383ad2b65`

## pseudocode

```c
__int64 __fastcall CServerEnum::EnumServers(
        CServerEnum *this,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        char *a5,
        unsigned int a6)
{
  unsigned int v9; // r15d
  DWORD TickCount; // r12d
  WCHAR *v12; // rbx
  DWORD v13; // esi
  DWORD v14; // edx
  __int64 v15; // rax
  SSRP::ServerEnum *v16; // rax
  SSRP::ServerEnum *v18; // r13
  __int64 v19; // rcx
  __int64 v20; // rsi
  unsigned __int16 *v21; // r14
  DWORD v22; // r11d
  unsigned __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // rdx
  _WORD *v26; // rcx
  __int16 v27; // ax
  __int64 v28; // r13
  signed int LastError; // eax
  const wchar_t *v30; // r14
  unsigned __int64 v31; // r12
  unsigned __int64 v32; // rbx
  unsigned __int64 *v33; // rsi
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // r8
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rax
  unsigned __int8 *v38; // rcx
  wchar_t v39; // ax
  __int64 v40; // rax
  unsigned __int64 *v41; // rsi
  __int64 v42; // rcx
  unsigned __int64 v43; // r8
  unsigned __int64 v44; // rcx
  unsigned __int64 v45; // rax
  unsigned __int8 *v46; // rcx
  unsigned __int64 v47; // rdx
  char v49; // al
  __int64 v50; // rdx
  char v51; // al
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nSize; // [rsp+44h] [rbp-BCh] BYREF
  int v54; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *Src; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v56; // [rsp+58h] [rbp-A8h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  SSRP::ServerEnum *v58; // [rsp+68h] [rbp-98h]
  WCHAR Buffer[136]; // [rsp+70h] [rbp-90h] BYREF

  v9 = 0;
  v54 = 1;
  memset(Buffer, 0, 258);
  TickCount = GetTickCount();
  if ( a4 && (!a2 || !*a2) )
  {
    v12 = (WCHAR *)*((_QWORD *)this + 1);
    cchValueName = *((_DWORD *)this + 4);
    hKey = 0;
    v13 = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSSQLServer\\Client\\ConnectTo", 0, 0x20019u, &hKey) )
    {
      for ( ; cchValueName; cchValueName = *((_DWORD *)this + 4) - *((_DWORD *)this + 6) )
      {
        v14 = v13++;
        if ( RegEnumValueW(hKey, v14, v12, &cchValueName, 0, 0, 0, 0) )
          break;
        if ( cchValueName
          && _wcsicmp(v12, L"Default")
          && _wcsicmp(v12, L"DSQUERY")
          && _wcsicmp(v12, L"SqlLocalizationFile")
          && _wcsicmp(v12, L"AutoAnsiToOem") )
        {
          v15 = cchValueName + 1;
          *((_QWORD *)this + 3) += v15;
          v12 += v15;
        }
      }
    }
  }
  v16 = SNIServerEnumOpenEx(a2, a3);
  v58 = v16;
  if ( v16 )
  {
    v18 = v16;
    while ( 1 )
    {
      v19 = *((_QWORD *)this + 3);
      v20 = *((_QWORD *)this + 2) - v19;
      v21 = (unsigned __int16 *)(*((_QWORD *)this + 1) + 2 * v19);
      if ( a6 != -1 )
      {
        v22 = GetTickCount();
        if ( v22 - TickCount >= a6 )
          break;
        a6 -= v22 - TickCount;
        TickCount = v22;
      }
      *((_QWORD *)this + 3) += (int)SNIServerEnumReadEx(v18, v21, v20, &v54, a6);
      if ( !v54 )
        break;
      v23 = *((_QWORD *)this + 2);
      if ( v23 >= 0x72326 )
        break;
      v24 = ((__int64 (__fastcall *)(struct IMalloc *, _QWORD, unsigned __int64))g_pMO->lpVtbl->Realloc)(
              g_pMO,
              *((_QWORD *)this + 1),
              2 * v23 + 64500);
      if ( !v24 )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          bidTraceW(off_383B435B0[0], 171049, off_383B49128[0], 2147942414LL);
        v9 = -2147024882;
        goto LABEL_70;
      }
      *((_QWORD *)this + 2) += 32250LL;
      *((_QWORD *)this + 1) = v24;
    }
    if ( a5 )
    {
      v25 = 129;
      v26 = (_WORD *)((char *)this + 40);
      while ( v25 != -2147483517 )
      {
        v27 = *(_WORD *)((char *)v26 + a5 - ((char *)this + 40));
        if ( !v27 )
          break;
        *v26++ = v27;
        if ( !--v25 )
        {
          --v26;
          break;
        }
      }
      *v26 = 0;
      v28 = -1;
      do
        ++v28;
      while ( *((_WORD *)this + v28 + 20) );
      nSize = 129;
      if ( !GetComputerNameW(Buffer, &nSize) )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_70:
        SNIServerEnumClose(v58);
        return v9;
      }
    }
    else
    {
      v28 = 0;
    }
    v30 = (const wchar_t *)*((_QWORD *)this + 1);
    v31 = 0;
    if ( *((_QWORD *)this + 3) )
    {
      while ( 1 )
      {
        v32 = -1;
        do
          ++v32;
        while ( v30[v32] );
        v33 = *(unsigned __int64 **)this;
        Src = v30;
        v56 = v32;
        v34 = v33[1];
        v35 = v34 + 1;
        if ( v34 == -1 )
          break;
        if ( v35 > v33[2] )
        {
          v38 = CExtBaseBuffer::ReAllocItems((CExtBaseBuffer *)v33, v34 + 1);
        }
        else
        {
          v36 = v34 * *v33;
          if ( !is_mul_ok(v33[1], *v33) )
            break;
          v37 = v33[4];
          v38 = (unsigned __int8 *)(v37 + v36);
          if ( (unsigned __int64)v38 < v37 )
            break;
          v33[1] = v35;
        }
        if ( !v38 )
          break;
        memcpy(v38, &Src, *v33);
        if ( a5 )
        {
          if ( v32 >= nSize && !_wcsnicmp(v30, Buffer, nSize) )
          {
            v39 = v30[nSize];
            if ( !v39 || v39 == 59 )
            {
              if ( v39 == 59 )
              {
                StringCchPrintfW((unsigned __int16 *)this + 149, 0x101u, L"%s%s", (char *)this + 40, &v30[nSize]);
                Src = (const wchar_t *)((char *)this + 298);
                v40 = -1;
                do
                  ++v40;
                while ( *((_WORD *)this + v40 + 149) );
                v56 = v40;
              }
              else
              {
                v56 = v28;
                Src = (const wchar_t *)((char *)this + 40);
              }
              v41 = *(unsigned __int64 **)this;
              v42 = *(_QWORD *)(*(_QWORD *)this + 8LL);
              v43 = v42 + 1;
              if ( v42 == -1 )
              {
LABEL_72:
                v49 = bidGblFlags;
                if ( (bidGblFlags & 2) != 0 )
                {
                  if ( off_383B49128[0] )
                    bidTraceW(off_383B434D8[0], 693289, off_383B49128[0], 2147942414LL);
                  v49 = bidGblFlags;
                }
                v9 = -2147024882;
                if ( (v49 & 2) != 0 )
                {
                  v50 = 252937;
LABEL_78:
                  bidTraceHR(off_383B435B0[0], v50, 2147942414LL);
                  goto LABEL_70;
                }
                goto LABEL_70;
              }
              if ( v43 > v41[2] )
              {
                v46 = CExtBaseBuffer::ReAllocItems(*(CExtBaseBuffer **)this, v42 + 1);
              }
              else
              {
                v44 = v42 * *v41;
                if ( !is_mul_ok(*(_QWORD *)(*(_QWORD *)this + 8LL), *v41) )
                  goto LABEL_72;
                v45 = v41[4];
                v46 = (unsigned __int8 *)(v45 + v44);
                if ( (unsigned __int64)v46 < v45 )
                  goto LABEL_72;
                v41[1] = v43;
              }
              if ( !v46 )
                goto LABEL_72;
              memcpy(v46, &Src, *v41);
            }
          }
        }
        v31 += v32 + 1;
        v30 += v32 + 1;
        if ( v31 >= *((_QWORD *)this + 3) )
          goto LABEL_68;
      }
      v51 = bidGblFlags;
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_383B49128[0] )
          bidTraceW(off_383B434D8[0], 693289, off_383B49128[0], 2147942414LL);
        v51 = bidGblFlags;
      }
      v9 = -2147024882;
      if ( (v51 & 2) != 0 )
      {
        v50 = 218121;
        goto LABEL_78;
      }
    }
    else
    {
LABEL_68:
      v47 = *(_QWORD *)(*(_QWORD *)this + 8LL);
      if ( v47 > 2 )
        qsort((void *)(**(_QWORD **)this + *(_QWORD *)(*(_QWORD *)this + 32LL)), v47 - 1, 0x10u, EnumCompare);
    }
    goto LABEL_70;
  }
  return v9;
}

```

## disassembly

```asm
0x383ad2a70  mov     [rsp-8+arg_18], rbx
0x383ad2a75  push    rbp
0x383ad2a76  push    rsi
0x383ad2a77  push    rdi
0x383ad2a78  push    r12
0x383ad2a7a  push    r13
0x383ad2a7c  push    r14
0x383ad2a7e  push    r15
0x383ad2a80  lea     rbp, [rsp-90h]
0x383ad2a88  sub     rsp, 190h
0x383ad2a8f  mov     rax, cs:__security_cookie
0x383ad2a96  xor     rax, rsp
0x383ad2a99  mov     [rbp+0C0h+var_40], rax
0x383ad2aa0  mov     rdi, rcx
0x383ad2aa3  mov     r13d, r8d
0x383ad2aa6  mov     r14, rdx
0x383ad2aa9  lea     rcx, [rsp+1C0h+var_14E]; void *
0x383ad2aae  xor     r15d, r15d
0x383ad2ab1  xor     edx, edx; Val
0x383ad2ab3  mov     r8d, 100h; Size
0x383ad2ab9  mov     ebx, r9d
0x383ad2abc  mov     [rsp+1C0h+var_178], 1
0x383ad2ac4  mov     [rsp+1C0h+Buffer], r15w
0x383ad2aca  call    memset
0x383ad2acf  call    cs:__imp_GetTickCount
0x383ad2ad5  mov     r12d, eax
0x383ad2ad8  test    ebx, ebx
0x383ad2ada  jz      loc_383AD2BE7
0x383ad2ae0  test    r14, r14
0x383ad2ae3  jz      short loc_383AD2AEF
0x383ad2ae5  cmp     [r14], r15w
0x383ad2ae9  jnz     loc_383AD2BE7
0x383ad2aef  mov     eax, [rdi+10h]
0x383ad2af2  mov     rbx, [rdi+8]
0x383ad2af6  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\MSSQLServer\\Clien"...
0x383ad2afd  mov     [rsp+1C0h+cchValueName], eax
0x383ad2b01  lea     rax, [rsp+1C0h+hKey]
0x383ad2b06  mov     r9d, 20019h; samDesired
0x383ad2b0c  xor     r8d, r8d; ulOptions
0x383ad2b0f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x383ad2b16  mov     [rsp+1C0h+hKey], r15
0x383ad2b1b  mov     [rsp+1C0h+phkResult], rax; phkResult
0x383ad2b20  mov     esi, r15d
0x383ad2b23  call    cs:__imp_RegOpenKeyExW
0x383ad2b29  test    eax, eax
0x383ad2b2b  jnz     loc_383AD2BE7
0x383ad2b31  cmp     [rsp+1C0h+cchValueName], r15d
0x383ad2b36  jz      loc_383AD2BE7
0x383ad2b3c  nop     dword ptr [rax+00h]
0x383ad2b40  mov     rcx, [rsp+1C0h+hKey]; hKey
0x383ad2b45  mov     [rsp+1C0h+lpcbData], r15; lpcbData
0x383ad2b4a  mov     edx, esi; dwIndex
0x383ad2b4c  mov     [rsp+1C0h+lpData], r15; lpData
0x383ad2b51  lea     r9, [rsp+1C0h+cchValueName]; lpcchValueName
0x383ad2b56  mov     r8, rbx; lpValueName
0x383ad2b59  mov     [rsp+1C0h+lpType], r15; lpType
0x383ad2b5e  inc     esi
0x383ad2b60  mov     [rsp+1C0h+phkResult], r15; lpReserved
0x383ad2b65  call    cs:__imp_RegEnumValueW
0x383ad2b6b  test    eax, eax
0x383ad2b6d  jnz     short loc_383AD2BE7
0x383ad2b6f  cmp     [rsp+1C0h+cchValueName], r15d
0x383ad2b74  jz      short loc_383AD2BD7
0x383ad2b76  lea     rdx, aDefault_0; "Default"
0x383ad2b7d  mov     rcx, rbx; String1
0x383ad2b80  call    cs:__imp__wcsicmp
0x383ad2b86  test    eax, eax
0x383ad2b88  jz      short loc_383AD2BD7
0x383ad2b8a  lea     rdx, aDsquery; "DSQUERY"
0x383ad2b91  mov     rcx, rbx; String1
0x383ad2b94  call    cs:__imp__wcsicmp
0x383ad2b9a  test    eax, eax
0x383ad2b9c  jz      short loc_383AD2BD7
0x383ad2b9e  lea     rdx, aSqllocalizatio; "SqlLocalizationFile"
0x383ad2ba5  mov     rcx, rbx; String1
0x383ad2ba8  call    cs:__imp__wcsicmp
0x383ad2bae  test    eax, eax
0x383ad2bb0  jz      short loc_383AD2BD7
0x383ad2bb2  lea     rdx, aAutoansitooem; "AutoAnsiToOem"
0x383ad2bb9  mov     rcx, rbx; String1
0x383ad2bbc  call    cs:__imp__wcsicmp
0x383ad2bc2  test    eax, eax
0x383ad2bc4  jz      short loc_383AD2BD7
0x383ad2bc6  mov     eax, [rsp+1C0h+cchValueName]
0x383ad2bca  inc     eax
0x383ad2bcc  mov     r8d, eax
0x383ad2bcf  add     [rdi+18h], r8
0x383ad2bd3  lea     rbx, [rbx+rax*2]
0x383ad2bd7  mov     eax, [rdi+10h]
0x383ad2bda  sub     eax, [rdi+18h]
0x383ad2bdd  mov     [rsp+1C0h+cchValueName], eax
0x383ad2be1  jnz     loc_383AD2B40
0x383ad2be7  mov     edx, r13d
0x383ad2bea  mov     rcx, r14; lpWideCharStr
0x383ad2bed  call    SNIServerEnumOpenEx
0x383ad2bf2  mov     [rsp+1C0h+var_158], rax
0x383ad2bf7  test    rax, rax
0x383ad2bfa  jz      loc_383AD2F72
0x383ad2c00  mov     ebx, [rbp+0C0h+arg_28]
0x383ad2c06  mov     r13, rax
0x383ad2c09  nop     dword ptr [rax+00000000h]
0x383ad2c10  mov     rcx, [rdi+18h]
0x383ad2c14  mov     rsi, [rdi+10h]
0x383ad2c18  mov     rax, [rdi+8]
0x383ad2c1c  sub     rsi, rcx
0x383ad2c1f  lea     r14, [rax+rcx*2]
0x383ad2c23  cmp     ebx, 0FFFFFFFFh
0x383ad2c26  jz      short loc_383AD2C41
0x383ad2c28  call    cs:__imp_GetTickCount
0x383ad2c2e  mov     r11d, eax
0x383ad2c31  sub     eax, r12d
0x383ad2c34  cmp     eax, ebx
0x383ad2c36  jnb     loc_383AD2CEC
0x383ad2c3c  sub     ebx, eax
0x383ad2c3e  mov     r12d, r11d
0x383ad2c41  lea     r9, [rsp+1C0h+var_178]; int *
0x383ad2c46  mov     r8d, esi; int
0x383ad2c49  mov     rdx, r14; unsigned __int16 *
0x383ad2c4c  mov     rcx, r13; this
0x383ad2c4f  mov     dword ptr [rsp+1C0h+phkResult], ebx; int
0x383ad2c53  call    SNIServerEnumReadEx
0x383ad2c58  movsxd  rcx, eax
0x383ad2c5b  add     [rdi+18h], rcx
0x383ad2c5f  cmp     [rsp+1C0h+var_178], r15d
0x383ad2c64  jz      loc_383AD2CEC
0x383ad2c6a  mov     r8, [rdi+10h]
0x383ad2c6e  cmp     r8, 72326h
0x383ad2c75  jnb     short loc_383AD2CEC
0x383ad2c77  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383ad2c7e  mov     rdx, [rdi+8]
0x383ad2c82  lea     r8, ds:0FBF4h[r8*2]
0x383ad2c8a  mov     rax, [rcx]
0x383ad2c8d  call    qword ptr [rax+20h]
0x383ad2c90  test    rax, rax
0x383ad2c93  jz      short loc_383AD2CA6
0x383ad2c95  add     qword ptr [rdi+10h], 7DFAh
0x383ad2c9d  mov     [rdi+8], rax
0x383ad2ca1  jmp     loc_383AD2C10
0x383ad2ca6  test    byte ptr cs:_bidGblFlags, 2
0x383ad2cad  jz      short loc_383AD2CE1
0x383ad2caf  mov     rcx, cs:off_383B435B0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383ad2cb6  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383ad2cbd  test    rax, rax
0x383ad2cc0  jz      short loc_383AD2CE1
0x383ad2cc2  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383ad2cc9  mov     r9d, 8007000Eh
0x383ad2ccf  mov     edx, 29C29h
0x383ad2cd4  mov     dword ptr [rsp+1C0h+phkResult], 0A7h
0x383ad2cdc  call    _bidTraceW
0x383ad2ce1  mov     r15d, 8007000Eh
0x383ad2ce7  jmp     loc_383AD2F68
0x383ad2cec  mov     rax, [rbp+0C0h+arg_20]
0x383ad2cf3  test    rax, rax
0x383ad2cf6  jz      loc_383AD2D8C
0x383ad2cfc  lea     r9, [rdi+28h]
0x383ad2d00  mov     r8, rax
0x383ad2d03  mov     edx, 81h
0x383ad2d08  mov     rcx, r9
0x383ad2d0b  sub     r8, r9
0x383ad2d0e  xchg    ax, ax
0x383ad2d10  lea     rax, [rdx+7FFFFF7Dh]
0x383ad2d17  test    rax, rax
0x383ad2d1a  jz      short loc_383AD2D34
0x383ad2d1c  movzx   eax, word ptr [r8+rcx]
0x383ad2d21  test    ax, ax
0x383ad2d24  jz      short loc_383AD2D34
0x383ad2d26  mov     [rcx], ax
0x383ad2d29  add     rcx, 2
0x383ad2d2d  dec     rdx
0x383ad2d30  jnz     short loc_383AD2D10
0x383ad2d32  jmp     short loc_383AD2D39
0x383ad2d34  test    rdx, rdx
0x383ad2d37  jnz     short loc_383AD2D3D
0x383ad2d39  sub     rcx, 2
0x383ad2d3d  mov     [rcx], r15w
0x383ad2d41  or      r13, 0FFFFFFFFFFFFFFFFh
0x383ad2d45  inc     r13
0x383ad2d48  cmp     [r9+r13*2], r15w
0x383ad2d4d  jnz     short loc_383AD2D45
0x383ad2d4f  lea     rdx, [rsp+1C0h+nSize]; nSize
0x383ad2d54  lea     rcx, [rsp+1C0h+Buffer]; lpBuffer
0x383ad2d59  mov     [rsp+1C0h+nSize], 81h
0x383ad2d61  call    cs:__imp_GetComputerNameW
0x383ad2d67  test    eax, eax
0x383ad2d69  jnz     short loc_383AD2D8F
0x383ad2d6b  call    cs:__imp_GetLastError
0x383ad2d71  mov     r15d, eax
0x383ad2d74  test    eax, eax
0x383ad2d76  jle     loc_383AD2F68
0x383ad2d7c  movzx   r15d, ax
0x383ad2d80  or      r15d, 80070000h
0x383ad2d87  jmp     loc_383AD2F68
0x383ad2d8c  mov     r13, r15
0x383ad2d8f  mov     r14, [rdi+8]
0x383ad2d93  mov     r12, r15
0x383ad2d96  cmp     [rdi+18h], r15
0x383ad2d9a  jbe     loc_383AD2F3E
0x383ad2da0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x383ad2da4  inc     rbx
0x383ad2da7  cmp     [r14+rbx*2], r15w
0x383ad2dac  jnz     short loc_383AD2DA4
0x383ad2dae  mov     rsi, [rdi]
0x383ad2db1  mov     [rsp+1C0h+Src], r14
0x383ad2db6  mov     [rsp+1C0h+var_168], rbx
0x383ad2dbb  mov     rcx, [rsi+8]
0x383ad2dbf  lea     r8, [rcx+1]
0x383ad2dc3  cmp     r8, 1
0x383ad2dc7  jb      loc_383AD300B
0x383ad2dcd  cmp     r8, [rsi+10h]
0x383ad2dd1  ja      short loc_383AD2DFB
0x383ad2dd3  mov     rax, [rsi]
0x383ad2dd6  mul     rcx
0x383ad2dd9  mov     rcx, rax
0x383ad2ddc  test    rdx, rdx
0x383ad2ddf  jnz     loc_383AD300B
0x383ad2de5  mov     rax, [rsi+20h]
0x383ad2de9  add     rcx, rax
0x383ad2dec  cmp     rcx, rax
0x383ad2def  jb      loc_383AD300B
0x383ad2df5  mov     [rsi+8], r8
0x383ad2df9  jmp     short loc_383AD2E09
0x383ad2dfb  mov     rdx, r8; unsigned __int64
0x383ad2dfe  mov     rcx, rsi; this
0x383ad2e01  call    ?ReAllocItems@CExtBaseBuffer@@IEAAPEAE_K@Z; CExtBaseBuffer::ReAllocItems(unsigned __int64)
0x383ad2e06  mov     rcx, rax; void *
0x383ad2e09  test    rcx, rcx
0x383ad2e0c  jz      loc_383AD300B
0x383ad2e12  mov     r8, [rsi]; Size
0x383ad2e15  lea     rdx, [rsp+1C0h+Src]; Src
0x383ad2e1a  call    memcpy
0x383ad2e1f  cmp     [rbp+0C0h+arg_20], r15
0x383ad2e26  jz      loc_383AD2F26
0x383ad2e2c  mov     r8d, [rsp+1C0h+nSize]; MaxCount
0x383ad2e31  cmp     rbx, r8
0x383ad2e34  jb      loc_383AD2F26
0x383ad2e3a  lea     rdx, [rsp+1C0h+Buffer]; String2
0x383ad2e3f  mov     rcx, r14; String1
0x383ad2e42  call    cs:__imp__wcsnicmp
0x383ad2e48  test    eax, eax
0x383ad2e4a  jnz     loc_383AD2F26
0x383ad2e50  mov     eax, [rsp+1C0h+nSize]
0x383ad2e54  lea     rcx, [r14+rax*2]
0x383ad2e58  movzx   eax, word ptr [r14+rax*2]
0x383ad2e5d  test    ax, ax
0x383ad2e60  jz      short loc_383AD2E6C
0x383ad2e62  cmp     ax, 3Bh ; ';'
0x383ad2e66  jnz     loc_383AD2F26
0x383ad2e6c  cmp     ax, 3Bh ; ';'
0x383ad2e70  jnz     short loc_383AD2EB1
0x383ad2e72  mov     [rsp+1C0h+phkResult], rcx
0x383ad2e77  lea     rsi, [rdi+12Ah]
0x383ad2e7e  lea     r9, [rdi+28h]
0x383ad2e82  lea     r8, aSS_7; "%s%s"
0x383ad2e89  mov     edx, 101h; unsigned __int64
0x383ad2e8e  mov     rcx, rsi; unsigned __int16 *
0x383ad2e91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x383ad2e96  mov     [rsp+1C0h+Src], rsi
0x383ad2e9b  or      rax, 0FFFFFFFFFFFFFFFFh
0x383ad2e9f  nop
0x383ad2ea0  inc     rax
0x383ad2ea3  cmp     [rsi+rax*2], r15w
0x383ad2ea8  jnz     short loc_383AD2EA0
0x383ad2eaa  mov     [rsp+1C0h+var_168], rax
0x383ad2eaf  jmp     short loc_383AD2EBF
0x383ad2eb1  lea     rax, [rdi+28h]
0x383ad2eb5  mov     [rsp+1C0h+var_168], r13
0x383ad2eba  mov     [rsp+1C0h+Src], rax
0x383ad2ebf  mov     rsi, [rdi]
0x383ad2ec2  mov     rcx, [rsi+8]
0x383ad2ec6  lea     r8, [rcx+1]
0x383ad2eca  cmp     r8, 1
0x383ad2ece  jb      loc_383AD2F9F
0x383ad2ed4  cmp     r8, [rsi+10h]
0x383ad2ed8  ja      short loc_383AD2F02
0x383ad2eda  mov     rax, [rsi]
0x383ad2edd  mul     rcx
0x383ad2ee0  mov     rcx, rax
0x383ad2ee3  test    rdx, rdx
0x383ad2ee6  jnz     loc_383AD2F9F
0x383ad2eec  mov     rax, [rsi+20h]
0x383ad2ef0  add     rcx, rax
0x383ad2ef3  cmp     rcx, rax
0x383ad2ef6  jb      loc_383AD2F9F
0x383ad2efc  mov     [rsi+8], r8
0x383ad2f00  jmp     short loc_383AD2F10
0x383ad2f02  mov     rdx, r8; unsigned __int64
0x383ad2f05  mov     rcx, rsi; this
0x383ad2f08  call    ?ReAllocItems@CExtBaseBuffer@@IEAAPEAE_K@Z; CExtBaseBuffer::ReAllocItems(unsigned __int64)
0x383ad2f0d  mov     rcx, rax; void *
0x383ad2f10  test    rcx, rcx
0x383ad2f13  jz      loc_383AD2F9F
0x383ad2f19  mov     r8, [rsi]; Size
0x383ad2f1c  lea     rdx, [rsp+1C0h+Src]; Src
0x383ad2f21  call    memcpy
0x383ad2f26  inc     r12
0x383ad2f29  lea     r14, [r14+rbx*2]
0x383ad2f2d  add     r12, rbx
0x383ad2f30  add     r14, 2
0x383ad2f34  cmp     r12, [rdi+18h]
0x383ad2f38  jb      loc_383AD2DA0
  ... truncated ...
```
