# CConvenienceLogonEnrollmentData::CConvenienceLogonEnrollmentData(ushort const *,ushort const *)

- ea: `0x1800197cc`
- end: `0x1800198cb`
- name: `??0CConvenienceLogonEnrollmentData@@QEAA@PEBG0@Z`
- size: `255`
- prototype: `CConvenienceLogonEnrollmentData *__fastcall(CConvenienceLogonEnrollmentData *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006480`
- `0x18000b318`
- `0x1800104d0`
- `0x180018dac`
- `0x1800191c4`
- `0x180019274`

## callees

- `0x18000a0e4`
- `0x180018d64`
- `0x1800197cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019872`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800198a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019872`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800198a5`

## pseudocode

```c
CConvenienceLogonEnrollmentData *__fastcall CConvenienceLogonEnrollmentData::CConvenienceLogonEnrollmentData(
        CConvenienceLogonEnrollmentData *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned __int16 **v3; // r14
  HKEY *v4; // r12
  HKEY *v5; // r13
  unsigned __int64 v8; // rsi
  int v9; // edi
  int v10; // eax
  int v11; // eax
  unsigned __int16 **phkResult; // [rsp+20h] [rbp-68h]
  unsigned __int64 *v14; // [rsp+28h] [rbp-60h]
  unsigned int v15; // [rsp+30h] [rbp-58h]

  v3 = (unsigned __int16 **)((char *)this + 8);
  *(_QWORD *)this = &CPicturePasswordUserData::`vftable';
  *((_QWORD *)this + 1) = 0;
  v4 = (HKEY *)((char *)this + 24);
  v5 = (HKEY *)((char *)this + 40);
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = -2147467259;
  *((_QWORD *)this + 5) = 0;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( v8 + 1 < v8 )
  {
    v9 = -2147024362;
  }
  else
  {
    v9 = _AllocArray<unsigned short,CTLocalAllocPolicy>(this, a2, v8 + 1, (char *)this + 8);
    if ( v9 >= 0 )
      StringCchCopyNExW(*v3, v8 + 1, a2, v8, phkResult, v14, v15);
  }
  *((_DWORD *)this + 4) = v9;
  if ( v9 >= 0 )
  {
    v10 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\PicturePassword",
            0,
            8u,
            v4);
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    *((_DWORD *)this + 4) = v10;
    if ( v10 >= 0 )
    {
      v11 = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\PicturePassword",
              0,
              0xCu,
              v5);
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      *((_DWORD *)this + 8) = v11;
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800197cc  push    rbx
0x1800197ce  push    rbp
0x1800197cf  push    rsi
0x1800197d0  push    rdi
0x1800197d1  push    r12
0x1800197d3  push    r13
0x1800197d5  push    r14
0x1800197d7  push    r15
0x1800197d9  sub     rsp, 48h
0x1800197dd  xor     edi, edi
0x1800197df  lea     rax, ??_7CPicturePasswordUserData@@6B@; const CPicturePasswordUserData::`vftable'
0x1800197e6  lea     r14, [rcx+8]
0x1800197ea  mov     [rcx], rax
0x1800197ed  mov     [r14], rdi
0x1800197f0  lea     r12, [rcx+18h]
0x1800197f4  lea     r13, [rcx+28h]
0x1800197f8  mov     [r12], rdi
0x1800197fc  mov     dword ptr [rcx+20h], 80004005h
0x180019803  mov     r15, rdx
0x180019806  mov     [r13+0], rdi
0x18001980a  mov     rbx, rcx
0x18001980d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180019811  inc     rsi
0x180019814  cmp     [rdx+rsi*2], di
0x180019818  jnz     short loc_180019811
0x18001981a  lea     rbp, [rsi+1]
0x18001981e  cmp     rbp, rsi
0x180019821  jb      short loc_180019847
0x180019823  mov     r9, r14
0x180019826  mov     r8, rbp
0x180019829  call    ??$_AllocArray@GVCTLocalAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTLocalAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x18001982e  mov     edi, eax
0x180019830  test    eax, eax
0x180019832  js      short loc_18001984C
0x180019834  mov     rcx, [r14]; unsigned __int16 *
0x180019837  mov     r9, rsi; unsigned __int64
0x18001983a  mov     r8, r15; unsigned __int16 *
0x18001983d  mov     rdx, rbp; unsigned __int64
0x180019840  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180019845  jmp     short loc_18001984C
0x180019847  mov     edi, 80070216h
0x18001984c  mov     [rbx+10h], edi
0x18001984f  test    edi, edi
0x180019851  js      short loc_1800198B7
0x180019853  mov     rsi, 0FFFFFFFF80000002h
0x18001985a  mov     [rsp+88h+phkResult], r12; phkResult
0x18001985f  mov     rcx, rsi; hKey
0x180019862  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180019869  mov     r9d, 8; samDesired
0x18001986f  xor     r8d, r8d; ulOptions
0x180019872  call    cs:__imp_RegOpenKeyExW
0x180019878  mov     edi, 80070000h
0x18001987d  test    eax, eax
0x18001987f  jle     short loc_180019886
0x180019881  movzx   eax, ax
0x180019884  or      eax, edi
0x180019886  mov     [rbx+10h], eax
0x180019889  test    eax, eax
0x18001988b  js      short loc_1800198B7
0x18001988d  mov     r9d, 0Ch; samDesired
0x180019893  mov     [rsp+88h+phkResult], r13; phkResult
0x180019898  xor     r8d, r8d; ulOptions
0x18001989b  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800198a2  mov     rcx, rsi; hKey
0x1800198a5  call    cs:__imp_RegOpenKeyExW
0x1800198ab  test    eax, eax
0x1800198ad  jle     short loc_1800198B4
0x1800198af  movzx   eax, ax
0x1800198b2  or      eax, edi
0x1800198b4  mov     [rbx+20h], eax
0x1800198b7  mov     rax, rbx
0x1800198ba  add     rsp, 48h
0x1800198be  pop     r15
0x1800198c0  pop     r14
0x1800198c2  pop     r13
0x1800198c4  pop     r12
0x1800198c6  pop     rdi
0x1800198c7  pop     rsi
0x1800198c8  pop     rbp
0x1800198c9  pop     rbx
0x1800198ca  retn
```
