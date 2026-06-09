# RDCameraDeviceManager::RemoveRDCameraDevice(char const *)

- ea: `0x180032d10`
- end: `0x180032f2e`
- name: `?RemoveRDCameraDevice@RDCameraDeviceManager@@AEAAJPEBD@Z`
- size: `542`
- prototype: `__int64 __fastcall(RDCameraDeviceManager *this, const char *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180032520`

## callees

- `0x18000b8f8`
- `0x18000b98c`
- `0x18000f79c`
- `0x1800179a8`
- `0x180017dc8`
- `0x180032c44`
- `0x180032d10`
- `0x180047ef0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032dad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032dad`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180032d54`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180032d54`

## string_xrefs

- `0x180032eea`: `m_spRDCameraBus->RemoveDevice by Identity failed`

## pseudocode

```c
__int64 __fastcall RDCameraDeviceManager::RemoveRDCameraDevice(RDCameraDeviceManager *this, const char *a2)
{
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r8
  unsigned int v8; // eax
  int v9; // edx
  const char *v10; // rcx
  unsigned int v11; // eax
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-A8h]
  unsigned __int16 v14[40]; // [rsp+30h] [rbp-98h] BYREF
  WCHAR v15[28]; // [rsp+80h] [rbp-48h] BYREF

  if ( !MultiByteToWideChar(0, 0, a2, -1, v15, 27) )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      LastError = GetLastError();
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        43,
        WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
    }
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
    return v6;
  }
  LODWORD(lpWideCharStr) = *((_DWORD *)this + 149);
  v6 = StringCbPrintfW(v14, 0x4Cu, L"%s_%d", v15, lpWideCharStr);
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      return v6;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 44;
    v10 = "StringCbPrintfW failed";
LABEL_13:
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v9,
      (unsigned int)WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
      v8,
      (__int64)v10,
      v6);
    return v6;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      45,
      (unsigned int)WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
      v11,
      (__int64)v14);
  }
  LOBYTE(v7) = 1;
  v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 7) + 88LL))(
         *((_QWORD *)this + 7),
         v14,
         v7);
  if ( (v6 & 0x80000000) == 0 )
  {
    DeviceIdentityList::RemoveAndDeleteEntry((RDCameraDeviceManager *)((char *)this + 608), v14);
    return v6;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 46;
    v10 = "m_spRDCameraBus->RemoveDevice by Identity failed";
    goto LABEL_13;
  }
  return v6;
}

```

## disassembly

```asm
0x180032d10  mov     r11, rsp
0x180032d13  mov     [r11+18h], rbx
0x180032d17  mov     [r11+20h], rsi
0x180032d1b  push    rdi
0x180032d1c  sub     rsp, 0C0h
0x180032d23  mov     rax, cs:__security_cookie
0x180032d2a  xor     rax, rsp
0x180032d2d  mov     [rsp+0C8h+var_10], rax
0x180032d35  mov     rsi, rcx
0x180032d38  mov     [rsp+0C8h+cchWideChar], 1Bh; cchWideChar
0x180032d40  lea     rax, [r11-48h]
0x180032d44  mov     r8, rdx; lpMultiByteStr
0x180032d47  xor     edx, edx; dwFlags
0x180032d49  mov     [rsp+0C8h+lpWideCharStr], rax; lpWideCharStr
0x180032d4e  xor     ecx, ecx; CodePage
0x180032d50  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180032d54  call    cs:__imp_MultiByteToWideChar
0x180032d5a  test    eax, eax
0x180032d5c  jnz     short loc_180032DCB
0x180032d5e  mov     rax, cs:WPP_GLOBAL_Control
0x180032d65  lea     rdi, WPP_GLOBAL_Control
0x180032d6c  cmp     rax, rdi
0x180032d6f  jz      short loc_180032DAD
0x180032d71  test    byte ptr [rax+1Ch], 1
0x180032d75  jz      short loc_180032DAD
0x180032d77  cmp     byte ptr [rax+19h], 2
0x180032d7b  jb      short loc_180032DAD
0x180032d7d  call    cs:__imp_GetLastError
0x180032d83  mov     ebx, eax
0x180032d85  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180032d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032d91  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x180032d98  mov     edx, 2Bh ; '+'
0x180032d9d  mov     dword ptr [rsp+0C8h+lpWideCharStr], ebx
0x180032da1  mov     r9d, eax
0x180032da4  mov     rcx, [rcx+10h]
0x180032da8  call    WPP_SF_Dd
0x180032dad  call    cs:__imp_GetLastError
0x180032db3  mov     ebx, eax
0x180032db5  test    eax, eax
0x180032db7  jle     loc_180032F07
0x180032dbd  movzx   ebx, ax
0x180032dc0  or      ebx, 80070000h
0x180032dc6  jmp     loc_180032F07
0x180032dcb  mov     eax, [rsi+254h]
0x180032dd1  lea     r9, [rsp+0C8h+var_48]
0x180032dd9  lea     r8, aSD; "%s_%d"
0x180032de0  mov     dword ptr [rsp+0C8h+lpWideCharStr], eax
0x180032de4  mov     edx, 4Ch ; 'L'; unsigned __int64
0x180032de9  lea     rcx, [rsp+0C8h+var_98]; unsigned __int16 *
0x180032dee  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032df3  mov     ebx, eax
0x180032df5  test    eax, eax
0x180032df7  jns     short loc_180032E5D
0x180032df9  mov     rax, cs:WPP_GLOBAL_Control
0x180032e00  lea     rdi, WPP_GLOBAL_Control
0x180032e07  cmp     rax, rdi
0x180032e0a  jz      loc_180032F07
0x180032e10  test    byte ptr [rax+1Ch], 8
0x180032e14  jz      loc_180032F07
0x180032e1a  cmp     byte ptr [rax+19h], 2
0x180032e1e  jb      loc_180032F07
0x180032e24  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180032e29  mov     edx, 2Ch ; ','
0x180032e2e  lea     rcx, aStringcbprintf_0; "StringCbPrintfW failed"
0x180032e35  mov     [rsp+0C8h+cchWideChar], ebx
0x180032e39  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x180032e40  mov     [rsp+0C8h+lpWideCharStr], rcx
0x180032e45  mov     r9d, eax
0x180032e48  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e4f  mov     rcx, [rcx+10h]
0x180032e53  call    WPP_SF_DsD
0x180032e58  jmp     loc_180032F07
0x180032e5d  mov     rax, cs:WPP_GLOBAL_Control
0x180032e64  lea     rdi, WPP_GLOBAL_Control
0x180032e6b  cmp     rax, rdi
0x180032e6e  jz      short loc_180032EAA
0x180032e70  test    byte ptr [rax+1Ch], 1
0x180032e74  jz      short loc_180032EAA
0x180032e76  cmp     byte ptr [rax+19h], 4
0x180032e7a  jb      short loc_180032EAA
0x180032e7c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180032e81  lea     rcx, [rsp+0C8h+var_98]
0x180032e86  mov     edx, 2Dh ; '-'
0x180032e8b  mov     [rsp+0C8h+lpWideCharStr], rcx
0x180032e90  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x180032e97  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e9e  mov     r9d, eax
0x180032ea1  mov     rcx, [rcx+10h]
0x180032ea5  call    WPP_SF_DS
0x180032eaa  mov     rcx, [rsi+38h]
0x180032eae  lea     rdx, [rsp+0C8h+var_98]
0x180032eb3  mov     r8b, 1
0x180032eb6  mov     rax, [rcx]
0x180032eb9  mov     rax, [rax+58h]
0x180032ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ec2  mov     ebx, eax
0x180032ec4  test    eax, eax
0x180032ec6  jns     short loc_180032EF6
0x180032ec8  mov     rax, cs:WPP_GLOBAL_Control
0x180032ecf  cmp     rax, rdi
0x180032ed2  jz      short loc_180032F07
0x180032ed4  test    byte ptr [rax+1Ch], 8
0x180032ed8  jz      short loc_180032F07
0x180032eda  cmp     byte ptr [rax+19h], 2
0x180032ede  jb      short loc_180032F07
0x180032ee0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180032ee5  mov     edx, 2Eh ; '.'
0x180032eea  lea     rcx, aMSprdcamerabus; "m_spRDCameraBus->RemoveDevice by Identi"...
0x180032ef1  jmp     loc_180032E35
0x180032ef6  lea     rcx, [rsi+260h]; this
0x180032efd  lea     rdx, [rsp+0C8h+var_98]; unsigned __int16 *
0x180032f02  call    ?RemoveAndDeleteEntry@DeviceIdentityList@@QEAAXPEBG@Z; DeviceIdentityList::RemoveAndDeleteEntry(ushort const *)
0x180032f07  mov     eax, ebx
0x180032f09  mov     rcx, [rsp+0C8h+var_10]
0x180032f11  xor     rcx, rsp; StackCookie
0x180032f14  call    __security_check_cookie
0x180032f19  lea     r11, [rsp+0C8h+var_8]
0x180032f21  mov     rbx, [r11+20h]
0x180032f25  mov     rsi, [r11+28h]
0x180032f29  mov     rsp, r11
0x180032f2c  pop     rdi
0x180032f2d  retn
```
