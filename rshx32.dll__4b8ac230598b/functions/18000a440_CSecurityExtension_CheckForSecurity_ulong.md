# CSecurityExtension::_CheckForSecurity(ulong)

- ea: `0x18000a440`
- end: `0x18000a664`
- name: `?_CheckForSecurity@CSecurityExtension@@AEAAJK@Z`
- size: `548`
- prototype: `__int64 __fastcall(CSecurityExtension *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008d90`
- `0x180009c90`

## callees

- `0x1800064d0`
- `0x180008238`
- `0x180009148`
- `0x18000a440`
- `0x18001654c`
- `0x1800167b4`
- `0x18001d33a`
- `0x18001d370`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a622`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a622`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a630`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a630`

## pseudocode

```c
__int64 __fastcall CSecurityExtension::_CheckForSecurity(CSecurityExtension *this, unsigned int a2)
{
  void *v3; // r15
  unsigned int v4; // r9d
  unsigned __int16 *v5; // rcx
  bool v6; // zf
  unsigned int v7; // edi
  char v8; // si
  int v9; // eax
  int v10; // r14d
  int v11; // ecx
  int v12; // ecx
  int v13; // eax
  unsigned int v14; // eax
  unsigned int v16[4]; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int16 v17[264]; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v18; // [rsp+2A0h] [rbp+198h] BYREF

  v18 = a2;
  v16[0] = 8;
  v16[1] = 9;
  v3 = (void *)EnablePrivileges(v16, 2);
  memset_0(v17, 0, 0x208u);
  v5 = (unsigned __int16 *)*((_QWORD *)this + 8);
  v6 = *((_DWORD *)this + 7) == 1;
  v7 = 0;
  v16[0] = 0;
  if ( v6 )
  {
    GetFileInfo(v5, &v18, v17, v4, (int *)this + 18, (int *)this + 19);
    v8 = v18;
    if ( (v18 & 4) == 0 )
    {
      v10 = -2147023546;
      goto LABEL_7;
    }
    v9 = CheckFileAccess(*((const unsigned __int16 **)this + 8), v16);
  }
  else
  {
    v8 = 3;
    v9 = CheckPrinterAccess(v5, v16, v17, v4);
  }
  v7 = v16[0];
  v10 = v9;
LABEL_7:
  if ( v10 >= 0 )
  {
    if ( *((_DWORD *)this + 7) != 3 || (v7 & 0x10E0000) != 0 )
    {
      if ( (v8 & 0x10) != 0 )
        *((_DWORD *)this + 11) |= 0x400000u;
      if ( !v17[0] || (v10 = LocalAllocString((unsigned __int16 **)this + 6, v17), v10 >= 0) )
      {
        if ( *((_DWORD *)this + 7) == 3 || (v11 = *((_DWORD *)this + 11), (v11 & 0x400000) == 0) )
        {
          if ( (v7 & 0x60000) != 0x60000 )
            *((_DWORD *)this + 11) |= 8u;
          if ( (v7 & 0x80000) == 0 )
          {
            v13 = *((_DWORD *)this + 11);
            if ( (v7 & 0x20000) != 0 )
              v14 = v13 | 0x40;
            else
              v14 = v13 & 0xFFFFFFFE;
            *((_DWORD *)this + 11) = v14;
          }
          if ( (v7 & 0x1000000) == 0 )
            *((_DWORD *)this + 11) &= ~2u;
          if ( (v7 & 0x20000) == 0 )
            *((_DWORD *)this + 20) = 1;
        }
        else if ( !*((_DWORD *)this + 19) )
        {
          v12 = v11 | 0x4000000;
          *((_DWORD *)this + 11) = v12;
          if ( (v7 & 0x1020000) != 0x1020000 )
          {
            v12 |= 0x2000000u;
            *((_DWORD *)this + 11) = v12;
          }
          if ( (v7 & 0x60000) != 0x60000 )
            *((_DWORD *)this + 11) = v12 | 0x1000000;
        }
        if ( (v8 & 1) != 0 )
          *((_DWORD *)this + 11) |= 4u;
        if ( (v8 & 2) != 0 )
          *((_DWORD *)this + 11) |= 0x200u;
        if ( (v8 & 0xC) == 0xC )
          *((_DWORD *)this + 11) |= 0x60000000u;
      }
    }
    else
    {
      v10 = -2147024891;
    }
  }
  if ( v3 != (void *)-1LL )
  {
    SetThreadToken(0, v3);
    if ( v3 )
      CloseHandle(v3);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a440  mov     rax, rsp
0x18000a443  mov     [rax+18h], rbx
0x18000a447  mov     [rax+20h], rsi
0x18000a44b  mov     [rax+10h], edx
0x18000a44e  push    rbp
0x18000a44f  push    rdi
0x18000a450  push    r12
0x18000a452  push    r14
0x18000a454  push    r15
0x18000a456  lea     rbp, [rax-188h]
0x18000a45d  sub     rsp, 260h
0x18000a464  mov     rax, cs:__security_cookie
0x18000a46b  xor     rax, rsp
0x18000a46e  mov     [rbp+180h+var_30], rax
0x18000a475  mov     rbx, rcx
0x18000a478  mov     [rsp+280h+var_250], 8
0x18000a480  lea     rcx, [rsp+280h+var_250]
0x18000a485  mov     [rsp+280h+var_24C], 9
0x18000a48d  mov     edx, 2
0x18000a492  call    EnablePrivileges
0x18000a497  xor     edx, edx; Val
0x18000a499  lea     rcx, [rsp+280h+var_240]; void *
0x18000a49e  mov     r8d, 208h; Size
0x18000a4a4  mov     r15, rax
0x18000a4a7  call    memset_0
0x18000a4ac  mov     rcx, [rbx+40h]; pPrinterName
0x18000a4b0  lea     r8, [rsp+280h+var_240]; unsigned __int16 *
0x18000a4b5  xor     r12d, r12d
0x18000a4b8  cmp     dword ptr [rbx+1Ch], 1
0x18000a4bc  mov     edi, r12d
0x18000a4bf  mov     [rsp+280h+var_250], r12d
0x18000a4c4  jnz     short loc_18000A508
0x18000a4c6  lea     rax, [rbx+4Ch]
0x18000a4ca  lea     rdx, [rbx+48h]
0x18000a4ce  mov     [rsp+280h+var_258], rax; int *
0x18000a4d3  mov     [rsp+280h+var_260], rdx; int *
0x18000a4d8  lea     rdx, [rbp+180h+arg_8]; unsigned int *
0x18000a4df  call    ?GetFileInfo@@YAXPEBGPEAKPEAGKPEAH3@Z; GetFileInfo(ushort const *,ulong *,ushort *,ulong,int *,int *)
0x18000a4e4  mov     esi, [rbp+180h+arg_8]
0x18000a4ea  test    sil, 4
0x18000a4ee  jz      short loc_18000A500
0x18000a4f0  mov     rcx, [rbx+40h]; unsigned __int16 *
0x18000a4f4  lea     rdx, [rsp+280h+var_250]; unsigned int *
0x18000a4f9  call    ?CheckFileAccess@@YAJPEBGPEAK@Z; CheckFileAccess(ushort const *,ulong *)
0x18000a4fe  jmp     short loc_18000A517
0x18000a500  mov     r14d, 80070546h
0x18000a506  jmp     short loc_18000A51E
0x18000a508  lea     rdx, [rsp+280h+var_250]; unsigned int *
0x18000a50d  mov     esi, 3
0x18000a512  call    ?CheckPrinterAccess@@YAJPEBGPEAKPEAGK@Z; CheckPrinterAccess(ushort const *,ulong *,ushort *,ulong)
0x18000a517  mov     edi, [rsp+280h+var_250]
0x18000a51b  mov     r14d, eax
0x18000a51e  test    r14d, r14d
0x18000a521  js      loc_18000A617
0x18000a527  cmp     dword ptr [rbx+1Ch], 3
0x18000a52b  jnz     short loc_18000A540
0x18000a52d  test    edi, 10E0000h
0x18000a533  jnz     short loc_18000A540
0x18000a535  mov     r14d, 80070005h
0x18000a53b  jmp     loc_18000A617
0x18000a540  test    sil, 10h
0x18000a544  jz      short loc_18000A54B
0x18000a546  bts     dword ptr [rbx+2Ch], 16h
0x18000a54b  cmp     [rsp+280h+var_240], r12w
0x18000a551  jz      short loc_18000A56C
0x18000a553  lea     rcx, [rbx+30h]; unsigned __int16 **
0x18000a557  lea     rdx, [rsp+280h+var_240]; unsigned __int16 *
0x18000a55c  call    ?LocalAllocString@@YAJPEAPEAGPEBG@Z; LocalAllocString(ushort * *,ushort const *)
0x18000a561  mov     r14d, eax
0x18000a564  test    eax, eax
0x18000a566  js      loc_18000A617
0x18000a56c  cmp     dword ptr [rbx+1Ch], 3
0x18000a570  jz      short loc_18000A5B0
0x18000a572  mov     ecx, [rbx+2Ch]
0x18000a575  bt      ecx, 16h
0x18000a579  jnb     short loc_18000A5B0
0x18000a57b  cmp     [rbx+4Ch], r12d
0x18000a57f  jnz     short loc_18000A5F2
0x18000a581  mov     edx, 1020000h
0x18000a586  bts     ecx, 1Ah
0x18000a58a  mov     eax, edi
0x18000a58c  mov     [rbx+2Ch], ecx
0x18000a58f  and     eax, edx
0x18000a591  cmp     eax, edx
0x18000a593  jz      short loc_18000A59C
0x18000a595  bts     ecx, 19h
0x18000a599  mov     [rbx+2Ch], ecx
0x18000a59c  mov     edx, 60000h
0x18000a5a1  and     edi, edx
0x18000a5a3  cmp     edi, edx
0x18000a5a5  jz      short loc_18000A5F2
0x18000a5a7  bts     ecx, 18h
0x18000a5ab  mov     [rbx+2Ch], ecx
0x18000a5ae  jmp     short loc_18000A5F2
0x18000a5b0  mov     edx, 60000h
0x18000a5b5  mov     eax, edi
0x18000a5b7  and     eax, edx
0x18000a5b9  cmp     eax, edx
0x18000a5bb  jz      short loc_18000A5C1
0x18000a5bd  or      dword ptr [rbx+2Ch], 8
0x18000a5c1  bt      edi, 13h
0x18000a5c5  jb      short loc_18000A5DB
0x18000a5c7  bt      edi, 11h
0x18000a5cb  mov     eax, [rbx+2Ch]
0x18000a5ce  jb      short loc_18000A5D5
0x18000a5d0  and     eax, 0FFFFFFFEh
0x18000a5d3  jmp     short loc_18000A5D8
0x18000a5d5  or      eax, 40h
0x18000a5d8  mov     [rbx+2Ch], eax
0x18000a5db  bt      edi, 18h
0x18000a5df  jb      short loc_18000A5E5
0x18000a5e1  and     dword ptr [rbx+2Ch], 0FFFFFFFDh
0x18000a5e5  bt      edi, 11h
0x18000a5e9  jb      short loc_18000A5F2
0x18000a5eb  mov     dword ptr [rbx+50h], 1
0x18000a5f2  test    sil, 1
0x18000a5f6  jz      short loc_18000A5FC
0x18000a5f8  or      dword ptr [rbx+2Ch], 4
0x18000a5fc  test    sil, 2
0x18000a600  jz      short loc_18000A607
0x18000a602  bts     dword ptr [rbx+2Ch], 9
0x18000a607  and     esi, 0Ch
0x18000a60a  cmp     sil, 0Ch
0x18000a60e  jnz     short loc_18000A617
0x18000a610  or      dword ptr [rbx+2Ch], 60000000h
0x18000a617  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000a61b  jz      short loc_18000A636
0x18000a61d  mov     rdx, r15; Token
0x18000a620  xor     ecx, ecx; Thread
0x18000a622  call    cs:__imp_SetThreadToken
0x18000a628  test    r15, r15
0x18000a62b  jz      short loc_18000A636
0x18000a62d  mov     rcx, r15; hObject
0x18000a630  call    cs:__imp_CloseHandle
0x18000a636  mov     eax, r14d
0x18000a639  mov     rcx, [rbp+180h+var_30]
0x18000a640  xor     rcx, rsp; StackCookie
0x18000a643  call    __security_check_cookie
0x18000a648  lea     r11, [rsp+280h+var_20]
0x18000a650  mov     rbx, [r11+40h]
0x18000a654  mov     rsi, [r11+48h]
0x18000a658  mov     rsp, r11
0x18000a65b  pop     r15
0x18000a65d  pop     r14
0x18000a65f  pop     r12
0x18000a661  pop     rdi
0x18000a662  pop     rbp
0x18000a663  retn
```
