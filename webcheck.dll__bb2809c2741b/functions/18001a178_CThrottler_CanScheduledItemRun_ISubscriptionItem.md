# CThrottler::CanScheduledItemRun(ISubscriptionItem *)

- ea: `0x18001a178`
- end: `0x18001a413`
- name: `?CanScheduledItemRun@CThrottler@@AEAAJPEAUISubscriptionItem@@@Z`
- size: `667`
- prototype: `int(CThrottler *__hidden this, struct ISubscriptionItem *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001b0f8`

## callees

- `0x18001a178`
- `0x18001d8d0`
- `0x180027d0c`
- `0x180029280`

## import_xrefs

- `IEFRAME!__imp_SHRestricted2W` at `0x18001a21e`
- `IEFRAME!__imp_SHRestricted2W` at `0x18001a23c`
- `IEFRAME!__imp_SHRestricted2W` at `0x18001a2ed`
- `IEFRAME!__imp_SHRestricted2W` at `0x18001a2ff`
- `IEFRAME!__imp_SHRestricted2W` at `0x18001a21e`
- `IEFRAME!__imp_SHRestricted2W` at `0x18001a23c`
- `IEFRAME!__imp_SHRestricted2W` at `0x18001a2ed`
- `IEFRAME!__imp_SHRestricted2W` at `0x18001a2ff`
- `KERNEL32!SystemTimeToFileTime` at `0x18001a293`
- `KERNEL32!SystemTimeToFileTime` at `0x18001a33c`
- `KERNEL32!SystemTimeToFileTime` at `0x18001a372`
- `KERNEL32!SystemTimeToFileTime` at `0x18001a39f`
- `KERNEL32!SystemTimeToFileTime` at `0x18001a293`
- `KERNEL32!SystemTimeToFileTime` at `0x18001a33c`
- `KERNEL32!SystemTimeToFileTime` at `0x18001a372`
- `KERNEL32!SystemTimeToFileTime` at `0x18001a39f`
- `KERNEL32!GetLocalTime` at `0x18001a26f`
- `KERNEL32!GetLocalTime` at `0x18001a32e`
- `KERNEL32!GetLocalTime` at `0x18001a26f`
- `KERNEL32!GetLocalTime` at `0x18001a32e`
- `SHLWAPI!SHGetValueW` at `0x18001a1fa`
- `SHLWAPI!SHGetValueW` at `0x18001a1fa`

## string_xrefs

- `0x18001a1a0`: `NoScheduledUpdates`

## pseudocode

```c
__int64 __fastcall CThrottler::CanScheduledItemRun(CThrottler *this, struct ISubscriptionItem *a2)
{
  unsigned int v3; // ebx
  unsigned int v4; // eax
  const unsigned __int16 *v5; // rdx
  __int64 v6; // rbx
  __int64 v7; // rcx
  int v8; // esi
  int v9; // eax
  unsigned __int16 v10; // di
  struct _FILETIME FileTime; // [rsp+38h] [rbp-19h] BYREF
  struct _FILETIME v13; // [rsp+40h] [rbp-11h] BYREF
  struct _FILETIME v14; // [rsp+48h] [rbp-9h] BYREF
  int pvData; // [rsp+50h] [rbp-1h] BYREF
  DWORD v16; // [rsp+54h] [rbp+3h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp+7h] BYREF
  WCHAR pszValue[20]; // [rsp+68h] [rbp+17h] BYREF

  wcscpy(pszValue, L"NoScheduledUpdtes");
  pvData = 0;
  v16 = 4;
  if ( !SHGetValueW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Webcheck",
          pszValue,
          0,
          &pvData,
          &v16)
    && pvData )
  {
    return (unsigned int)-2146693244;
  }
  if ( (unsigned int)SHRestricted2W(1342177290, 0, 0) )
    return (unsigned int)-2146693243;
  v4 = SHRestricted2W(1342177299, 0, 0);
  v6 = v4;
  if ( v4 )
  {
    v14 = 0;
    if ( (int)ReadDATE(a2, v5, (double *)&v14) >= 0 )
    {
      SystemTime = 0;
      GetLocalTime(&SystemTime);
      v13 = 0;
      FileTime = 0;
      VariantTimeToFileTime(v7, &v13);
      SystemTimeToFileTime(&SystemTime, &FileTime);
      if ( *(_QWORD *)&FileTime - *(_QWORD *)&v13 < 600000000 * v6 )
        return (unsigned int)-2146693242;
    }
  }
  v3 = 0;
  v8 = SHRestricted2W(1342177300, 0, 0);
  v9 = SHRestricted2W(1342177301, 0, 0);
  v10 = v9;
  if ( v8 && v9 )
  {
    FileTime = 0;
    v14 = 0;
    SystemTime = 0;
    v13 = 0;
    GetLocalTime(&SystemTime);
    SystemTimeToFileTime(&SystemTime, &FileTime);
    SystemTime.wMilliseconds = 0;
    SystemTime.wHour = (unsigned __int16)v8 / 0x3Cu;
    *(_DWORD *)&SystemTime.wMinute = (unsigned __int16)v8 % 0x3Cu;
    SystemTimeToFileTime(&SystemTime, &v14);
    SystemTime.wHour = v10 / 0x3Cu;
    SystemTime.wMinute = v10 % 0x3Cu;
    SystemTimeToFileTime(&SystemTime, &v13);
    if ( *(_QWORD *)&v14 > *(__int64 *)&v13 )
    {
      if ( *(_QWORD *)&FileTime <= *(__int64 *)&v13 || *(_QWORD *)&FileTime >= *(__int64 *)&v14 )
        return (unsigned int)-2146693241;
    }
    else if ( *(_QWORD *)&FileTime >= *(__int64 *)&v14 && *(_QWORD *)&FileTime <= *(__int64 *)&v13 )
    {
      return (unsigned int)-2146693241;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18001a178  mov     r11, rsp
0x18001a17b  mov     [r11+8], rbx
0x18001a17f  mov     [r11+18h], rsi
0x18001a183  push    rbp
0x18001a184  push    rdi
0x18001a185  push    r14
0x18001a187  lea     rbp, [r11-5Fh]
0x18001a18b  sub     rsp, 90h
0x18001a192  mov     rax, cs:__security_cookie
0x18001a199  xor     rax, rsp
0x18001a19c  mov     [rbp+57h+var_18], rax
0x18001a1a0  movups  xmm0, xmmword ptr cs:aNoscheduledupd; "NoScheduledUpdates"
0x18001a1a7  lea     rax, [rbp+57h+var_54]
0x18001a1ab  mov     rdi, rdx
0x18001a1ae  movups  xmm1, xmmword ptr cs:aNoscheduledupd+10h; "ledUpdates"
0x18001a1b5  mov     [r11-80h], rax
0x18001a1b9  lea     r8, [rbp+57h+pszValue]; pszValue
0x18001a1bd  movups  xmmword ptr [rbp+57h+pszValue], xmm0
0x18001a1c1  lea     rax, [rbp+57h+var_58]
0x18001a1c5  xor     r14d, r14d
0x18001a1c8  movsd   xmm0, qword ptr cs:aNoscheduledupd+1Eh; "tes"
0x18001a1d0  lea     rdx, ?c_szRegKey@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001a1d7  movups  [rbp+57h+var_30], xmm1
0x18001a1db  xor     r9d, r9d; pdwType
0x18001a1de  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001a1e5  movsd   qword ptr [rbp+57h+var_30+0Eh], xmm0
0x18001a1ea  mov     [rbp+57h+var_58], r14d
0x18001a1ee  mov     [rbp+57h+var_54], 4
0x18001a1f5  mov     [rsp+0A0h+pvData], rax; pvData
0x18001a1fa  call    cs:__imp_SHGetValueW
0x18001a200  test    eax, eax
0x18001a202  jnz     short loc_18001A214
0x18001a204  cmp     [rbp+57h+var_58], r14d
0x18001a208  jz      short loc_18001A214
0x18001a20a  mov     ebx, 800C0F84h
0x18001a20f  jmp     loc_18001A3ED
0x18001a214  xor     r8d, r8d
0x18001a217  xor     edx, edx
0x18001a219  mov     ecx, 5000000Ah
0x18001a21e  call    cs:__imp_SHRestricted2W
0x18001a224  test    eax, eax
0x18001a226  jz      short loc_18001A232
0x18001a228  mov     ebx, 800C0F85h
0x18001a22d  jmp     loc_18001A3ED
0x18001a232  xor     r8d, r8d
0x18001a235  xor     edx, edx
0x18001a237  mov     ecx, 50000013h
0x18001a23c  call    cs:__imp_SHRestricted2W
0x18001a242  mov     ebx, eax
0x18001a244  test    eax, eax
0x18001a246  jz      loc_18001A2E0
0x18001a24c  xorps   xmm0, xmm0
0x18001a24f  lea     r8, [rbp+57h+var_60]; double *
0x18001a253  mov     rcx, rdi; struct ISubscriptionItem *
0x18001a256  movsd   qword ptr [rbp+57h+var_60.dwLowDateTime], xmm0
0x18001a25b  call    ?ReadDATE@@YAJPEAUISubscriptionItem@@PEBGPEAN@Z; ReadDATE(ISubscriptionItem *,ushort const *,double *)
0x18001a260  test    eax, eax
0x18001a262  js      short loc_18001A2E0
0x18001a264  xorps   xmm0, xmm0
0x18001a267  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001a26b  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001a26f  call    cs:__imp_GetLocalTime
0x18001a275  movsd   xmm0, qword ptr [rbp+57h+var_60.dwLowDateTime]
0x18001a27a  lea     rdx, [rbp+57h+var_68]
0x18001a27e  mov     qword ptr [rbp+57h+var_68.dwLowDateTime], r14
0x18001a282  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x18001a286  call    VariantTimeToFileTime
0x18001a28b  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18001a28f  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001a293  call    cs:__imp_SystemTimeToFileTime
0x18001a299  mov     eax, [rbp+57h+FileTime.dwLowDateTime]
0x18001a29c  mov     r8d, [rbp+57h+FileTime.dwHighDateTime]
0x18001a2a0  mov     ecx, [rbp+57h+var_68.dwHighDateTime]
0x18001a2a3  shl     r8, 20h
0x18001a2a7  or      r8, rax
0x18001a2aa  shl     rcx, 20h
0x18001a2ae  mov     eax, [rbp+57h+var_68.dwLowDateTime]
0x18001a2b1  or      rcx, rax
0x18001a2b4  sub     r8, rcx
0x18001a2b7  imul    rcx, rbx, 23C34600h
0x18001a2be  mov     rdx, r8
0x18001a2c1  mov     eax, r8d
0x18001a2c4  sar     rdx, 20h
0x18001a2c8  mov     edx, edx
0x18001a2ca  shl     rdx, 20h
0x18001a2ce  or      rdx, rax
0x18001a2d1  cmp     rdx, rcx
0x18001a2d4  jge     short loc_18001A2E0
0x18001a2d6  mov     ebx, 800C0F86h
0x18001a2db  jmp     loc_18001A3ED
0x18001a2e0  xor     r8d, r8d
0x18001a2e3  xor     edx, edx
0x18001a2e5  mov     ecx, 50000014h
0x18001a2ea  mov     ebx, r14d
0x18001a2ed  call    cs:__imp_SHRestricted2W
0x18001a2f3  xor     r8d, r8d
0x18001a2f6  xor     edx, edx
0x18001a2f8  mov     ecx, 50000015h
0x18001a2fd  mov     esi, eax
0x18001a2ff  call    cs:__imp_SHRestricted2W
0x18001a305  mov     edi, eax
0x18001a307  test    esi, esi
0x18001a309  jz      loc_18001A3ED
0x18001a30f  test    eax, eax
0x18001a311  jz      loc_18001A3ED
0x18001a317  xorps   xmm0, xmm0
0x18001a31a  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x18001a31e  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001a322  mov     qword ptr [rbp+57h+var_60.dwLowDateTime], r14
0x18001a326  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001a32a  mov     qword ptr [rbp+57h+var_68.dwLowDateTime], r14
0x18001a32e  call    cs:__imp_GetLocalTime
0x18001a334  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18001a338  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001a33c  call    cs:__imp_SystemTimeToFileTime
0x18001a342  movzx   r8d, si
0x18001a346  mov     esi, 88888889h
0x18001a34b  mov     eax, esi
0x18001a34d  mov     dword ptr [rbp+57h+SystemTime.wSecond], r14d
0x18001a351  mul     r8d
0x18001a354  shr     edx, 5
0x18001a357  movzx   ecx, dx
0x18001a35a  mov     [rbp+57h+SystemTime.wHour], dx
0x18001a35e  imul    edx, ecx, 3Ch ; '<'
0x18001a361  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001a365  sub     r8w, dx
0x18001a369  lea     rdx, [rbp+57h+var_60]; lpFileTime
0x18001a36d  mov     [rbp+57h+SystemTime.wMinute], r8w
0x18001a372  call    cs:__imp_SystemTimeToFileTime
0x18001a378  movzx   r8d, di
0x18001a37c  mov     eax, esi
0x18001a37e  mul     r8d
0x18001a381  shr     edx, 5
0x18001a384  movzx   eax, dx
0x18001a387  imul    ecx, eax, 3Ch ; '<'
0x18001a38a  mov     [rbp+57h+SystemTime.wHour], dx
0x18001a38e  lea     rdx, [rbp+57h+var_68]; lpFileTime
0x18001a392  sub     r8w, cx
0x18001a396  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001a39a  mov     [rbp+57h+SystemTime.wMinute], r8w
0x18001a39f  call    cs:__imp_SystemTimeToFileTime
0x18001a3a5  mov     eax, [rbp+57h+var_68.dwLowDateTime]
0x18001a3a8  mov     edx, [rbp+57h+var_68.dwHighDateTime]
0x18001a3ab  mov     r8d, [rbp+57h+var_60.dwHighDateTime]
0x18001a3af  mov     ecx, [rbp+57h+FileTime.dwHighDateTime]
0x18001a3b2  shl     rdx, 20h
0x18001a3b6  or      rdx, rax
0x18001a3b9  shl     r8, 20h
0x18001a3bd  mov     eax, [rbp+57h+var_60.dwLowDateTime]
0x18001a3c0  or      r8, rax
0x18001a3c3  shl     rcx, 20h
0x18001a3c7  mov     eax, [rbp+57h+FileTime.dwLowDateTime]
0x18001a3ca  or      rcx, rax
0x18001a3cd  cmp     r8, rdx
0x18001a3d0  jg      short loc_18001A3DE
0x18001a3d2  cmp     rcx, r8
0x18001a3d5  jl      short loc_18001A3ED
0x18001a3d7  cmp     rcx, rdx
0x18001a3da  jg      short loc_18001A3ED
0x18001a3dc  jmp     short loc_18001A3E8
0x18001a3de  cmp     rcx, rdx
0x18001a3e1  jle     short loc_18001A3E8
0x18001a3e3  cmp     rcx, r8
0x18001a3e6  jl      short loc_18001A3ED
0x18001a3e8  mov     ebx, 800C0F87h
0x18001a3ed  mov     eax, ebx
0x18001a3ef  mov     rcx, [rbp+57h+var_18]
0x18001a3f3  xor     rcx, rsp; StackCookie
0x18001a3f6  call    __security_check_cookie
0x18001a3fb  lea     r11, [rsp+0A0h+var_10]
0x18001a403  mov     rbx, [r11+20h]
0x18001a407  mov     rsi, [r11+30h]
0x18001a40b  mov     rsp, r11
0x18001a40e  pop     r14
0x18001a410  pop     rdi
0x18001a411  pop     rbp
0x18001a412  retn
```
