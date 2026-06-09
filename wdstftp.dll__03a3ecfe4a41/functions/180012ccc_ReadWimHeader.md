# ReadWimHeader

- ea: `0x180012ccc`
- end: `0x180012fe9`
- name: `ReadWimHeader`
- size: `797`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18000db70`
- `0x18000f7c4`

## callees

- `0x180010938`
- `0x180011880`
- `0x180011904`
- `0x180011bb8`
- `0x180012304`
- `0x180012c1c`
- `0x180012ccc`
- `0x1800131c4`
- `0x1800132a8`
- `0x180017344`
- `0x1800607b0`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012d93`
- `KERNEL32!GetLastError` at `0x180012d93`
- `KERNEL32!SetLastError` at `0x180012fac`
- `KERNEL32!SetLastError` at `0x180012fac`

## string_xrefs

- `0x180012dd3`: `ReadWimHeader`
- `0x180012f6b`: `ReadWimHeader`
- `0x180012de3`: `cannot read WIM header`

## pseudocode

```c
__int64 __fastcall ReadWimHeader(__int64 a1, int a2)
{
  unsigned int v4; // r15d
  int WIMHeaderLock; // r12d
  DWORD v6; // esi
  void *WimFileHandle; // rax
  void *v8; // rax
  DWORD LastError; // eax
  int v10; // r8d
  NTSTATUS Status; // edx
  __int64 WimHeader; // rax
  int WimPath; // r8d
  void *v14; // rax
  _BYTE v16[32]; // [rsp+50h] [rbp-118h] BYREF
  __int64 v17; // [rsp+70h] [rbp-F8h] BYREF
  unsigned int v18; // [rsp+78h] [rbp-F0h]
  int v19; // [rsp+7Ch] [rbp-ECh]
  int v20; // [rsp+80h] [rbp-E8h]
  int v21; // [rsp+84h] [rbp-E4h]
  __int128 v22; // [rsp+88h] [rbp-E0h]
  __int16 v23; // [rsp+98h] [rbp-D0h]
  __int16 v24; // [rsp+9Ah] [rbp-CEh]
  int v25; // [rsp+9Ch] [rbp-CCh]
  __int64 v26; // [rsp+A0h] [rbp-C8h]
  __int64 v27; // [rsp+A8h] [rbp-C0h]
  __int64 v28; // [rsp+B0h] [rbp-B8h]
  __int64 v29; // [rsp+B8h] [rbp-B0h]
  __int64 v30; // [rsp+C0h] [rbp-A8h]
  __int64 v31; // [rsp+C8h] [rbp-A0h]
  __int64 v32; // [rsp+D0h] [rbp-98h]
  __int64 v33; // [rsp+D8h] [rbp-90h]
  __int64 v34; // [rsp+E0h] [rbp-88h]
  int v35; // [rsp+E8h] [rbp-80h]
  __int64 v36; // [rsp+ECh] [rbp-7Ch]
  __int64 v37; // [rsp+F4h] [rbp-74h]
  __int64 v38; // [rsp+FCh] [rbp-6Ch]

  v4 = 1;
  WIMHeaderLock = 0;
  memset_0(&v17, 0, 0xD0u);
  memset_0(v16, 0, sizeof(v16));
  v6 = 0;
  if ( !a2 && (GetFlagsAndAttributes(a1) & 0x40) != 0 )
  {
    WimFileHandle = (void *)GetWimFileHandle(a1);
    WIMHeaderLock = GetWIMHeaderLock(WimFileHandle);
  }
  v8 = (void *)GetWimFileHandle(a1);
  if ( (unsigned int)ReadWriteData(v8, 0) )
  {
    if ( v17 == 0x4D4957534DLL && v18 >= 0xD0 && (unsigned int)SupportedVersion(a1, &v17) )
    {
      WimHeader = GetWimHeader(a1);
      *(_QWORD *)WimHeader = v17;
      *(_DWORD *)(WimHeader + 8) = v18;
      *(_DWORD *)(WimHeader + 12) = v19;
      *(_DWORD *)(WimHeader + 16) = v20;
      *(_DWORD *)(WimHeader + 20) = v21;
      *(_OWORD *)(WimHeader + 24) = v22;
      *(_WORD *)(WimHeader + 40) = v23;
      *(_WORD *)(WimHeader + 42) = v24;
      *(_DWORD *)(WimHeader + 44) = v25;
      *(_DWORD *)(WimHeader + 240) = v35;
      *(_QWORD *)(WimHeader + 56) = v26;
      *(_QWORD *)(WimHeader + 64) = v27;
      *(_DWORD *)(WimHeader + 84) = 1;
      *(_QWORD *)(WimHeader + 72) = v28;
      *(_QWORD *)(WimHeader + 120) = v29;
      *(_QWORD *)(WimHeader + 128) = v30;
      *(_DWORD *)(WimHeader + 148) = 1;
      *(_QWORD *)(WimHeader + 136) = v31;
      *(_QWORD *)(WimHeader + 184) = v32;
      *(_QWORD *)(WimHeader + 192) = v33;
      *(_DWORD *)(WimHeader + 212) = 1;
      *(_QWORD *)(WimHeader + 200) = v34;
      *(_QWORD *)(WimHeader + 256) = v36;
      *(_QWORD *)(WimHeader + 264) = v37;
      *(_DWORD *)(WimHeader + 284) = 1;
      *(_QWORD *)(WimHeader + 272) = v38;
    }
    else
    {
      v4 = 0;
      v6 = 11;
      WimPath = GetWimPath(a1);
      WIMLogMsg(2, 0, WimPath, (int)L"version/header mismatch", -2147024885, (__int64)L"ReadWimHeader", 1856);
    }
  }
  else
  {
    v4 = 0;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError == 997 || LastError == 38 )
      v6 = 11;
    v10 = GetWimPath(a1);
    WIMLogMsg(2, 0, v10, (int)L"cannot read WIM header", Status, (__int64)L"ReadWimHeader", 1844);
  }
  if ( WIMHeaderLock )
  {
    v14 = (void *)GetWimFileHandle(a1);
    ReleaseWIMHeaderLock(v14);
  }
  if ( v6 )
    SetLastError(v6);
  return v4;
}

```

## disassembly

```asm
0x180012ccc  mov     [rsp+arg_8], rbx
0x180012cd1  mov     [rsp+arg_10], rsi
0x180012cd6  mov     [rsp+arg_18], rdi
0x180012cdb  push    r12
0x180012cdd  push    r14
0x180012cdf  push    r15
0x180012ce1  sub     rsp, 150h
0x180012ce8  mov     rax, cs:__security_cookie
0x180012cef  xor     rax, rsp
0x180012cf2  mov     [rsp+168h+var_28], rax
0x180012cfa  mov     edi, edx
0x180012cfc  mov     r14, rcx
0x180012cff  mov     [rsp+168h+var_120], rcx
0x180012d04  mov     r15d, 1
0x180012d0a  xor     r12d, r12d
0x180012d0d  mov     [rsp+168h+var_128], r12d
0x180012d12  xor     edx, edx; Val
0x180012d14  mov     r8d, 0D0h; Size
0x180012d1a  lea     rcx, [rsp+168h+var_F8]; void *
0x180012d1f  call    memset_0
0x180012d24  xor     edx, edx; Val
0x180012d26  lea     r8d, [r15+1Fh]; Size
0x180012d2a  lea     rcx, [rsp+168h+var_118]; void *
0x180012d2f  call    memset_0
0x180012d34  xor     esi, esi
0x180012d36  mov     rbx, 4D4957534Dh
0x180012d40  test    edi, edi
0x180012d42  jnz     short loc_180012D67
0x180012d44  mov     rcx, r14
0x180012d47  call    GetFlagsAndAttributes
0x180012d4c  test    al, 40h
0x180012d4e  jz      short loc_180012D67
0x180012d50  mov     rcx, r14
0x180012d53  call    GetWimFileHandle
0x180012d58  mov     rcx, rax; hFile
0x180012d5b  call    GetWIMHeaderLock
0x180012d60  mov     r12d, eax
0x180012d63  mov     [rsp+168h+var_128], eax
0x180012d67  mov     rcx, r14
0x180012d6a  call    GetWimFileHandle
0x180012d6f  and     [rsp+168h+Status], 0
0x180012d74  lea     r9, [rsp+168h+var_118]
0x180012d79  mov     r8d, 0D0h
0x180012d7f  lea     rdx, [rsp+168h+var_F8]
0x180012d84  mov     rcx, rax; hFile
0x180012d87  call    ReadWriteData
0x180012d8c  test    eax, eax
0x180012d8e  jnz     short loc_180012DEF
0x180012d90  xor     r15d, r15d
0x180012d93  call    cs:__imp_GetLastError
0x180012d9a  nop     dword ptr [rax+rax+00h]
0x180012d9f  mov     esi, eax
0x180012da1  cmp     eax, 3E5h
0x180012da6  jz      short loc_180012DAD
0x180012da8  cmp     eax, 26h ; '&'
0x180012dab  jnz     short loc_180012DB2
0x180012dad  mov     esi, 0Bh
0x180012db2  movzx   edx, si
0x180012db5  or      edx, 80070000h
0x180012dbb  test    esi, esi
0x180012dbd  cmovle  edx, esi
0x180012dc0  mov     rcx, r14
0x180012dc3  call    GetWimPath
0x180012dc8  mov     r8, rax
0x180012dcb  mov     [rsp+168h+var_138], 734h
0x180012dd3  lea     rax, aReadwimheader; "ReadWimHeader"
0x180012dda  mov     [rsp+168h+var_140], rax
0x180012ddf  mov     [rsp+168h+Status], edx
0x180012de3  lea     r9, aCannotReadWimH; "cannot read WIM header"
0x180012dea  jmp     loc_180012F86
0x180012def  cmp     [rsp+168h+var_F8], rbx
0x180012df4  jnz     loc_180012F51
0x180012dfa  cmp     [rsp+168h+var_F0], 0D0h
0x180012e02  jb      loc_180012F51
0x180012e08  lea     rdx, [rsp+168h+var_F8]
0x180012e0d  mov     rcx, r14
0x180012e10  call    SupportedVersion
0x180012e15  test    eax, eax
0x180012e17  jz      loc_180012F51
0x180012e1d  mov     rcx, r14
0x180012e20  call    GetWimHeader
0x180012e25  mov     rdx, rax
0x180012e28  mov     rax, [rsp+168h+var_F8]
0x180012e2d  mov     [rdx], rax
0x180012e30  mov     eax, [rsp+168h+var_F0]
0x180012e34  mov     [rdx+8], eax
0x180012e37  mov     eax, [rsp+168h+var_EC]
0x180012e3b  mov     [rdx+0Ch], eax
0x180012e3e  mov     eax, [rsp+168h+var_E8]
0x180012e45  mov     [rdx+10h], eax
0x180012e48  mov     eax, [rsp+168h+var_E4]
0x180012e4f  mov     [rdx+14h], eax
0x180012e52  movups  xmm0, [rsp+168h+var_E0]
0x180012e5a  movdqu  xmmword ptr [rdx+18h], xmm0
0x180012e5f  movzx   eax, [rsp+168h+var_D0]
0x180012e67  mov     [rdx+28h], ax
0x180012e6b  movzx   eax, [rsp+168h+var_CE]
0x180012e73  mov     [rdx+2Ah], ax
0x180012e77  mov     eax, [rsp+168h+var_CC]
0x180012e7e  mov     [rdx+2Ch], eax
0x180012e81  mov     eax, [rsp+168h+var_80]
0x180012e88  mov     [rdx+0F0h], eax
0x180012e8e  mov     rax, [rsp+168h+var_C8]
0x180012e96  mov     [rdx+38h], rax
0x180012e9a  mov     rax, [rsp+168h+var_C0]
0x180012ea2  mov     [rdx+40h], rax
0x180012ea6  mov     [rdx+54h], r15d
0x180012eaa  mov     rax, [rsp+168h+var_B8]
0x180012eb2  mov     [rdx+48h], rax
0x180012eb6  mov     rax, [rsp+168h+var_B0]
0x180012ebe  mov     [rdx+78h], rax
0x180012ec2  mov     rax, [rsp+168h+var_A8]
0x180012eca  mov     [rdx+80h], rax
0x180012ed1  mov     [rdx+94h], r15d
0x180012ed8  mov     rax, [rsp+168h+var_A0]
0x180012ee0  mov     [rdx+88h], rax
0x180012ee7  mov     rax, [rsp+168h+var_98]
0x180012eef  mov     [rdx+0B8h], rax
0x180012ef6  mov     rax, [rsp+168h+var_90]
0x180012efe  mov     [rdx+0C0h], rax
0x180012f05  mov     [rdx+0D4h], r15d
0x180012f0c  mov     rax, [rsp+168h+var_88]
0x180012f14  mov     [rdx+0C8h], rax
0x180012f1b  mov     rax, [rsp+168h+var_7C]
0x180012f23  mov     [rdx+100h], rax
0x180012f2a  mov     rax, [rsp+168h+var_74]
0x180012f32  mov     [rdx+108h], rax
0x180012f39  mov     [rdx+11Ch], r15d
0x180012f40  mov     rax, [rsp+168h+var_6C]
0x180012f48  mov     [rdx+110h], rax
0x180012f4f  jmp     short loc_180012F91
0x180012f51  xor     r15d, r15d
0x180012f54  lea     esi, [r15+0Bh]
0x180012f58  mov     rcx, r14
0x180012f5b  call    GetWimPath
0x180012f60  mov     r8, rax; int
0x180012f63  mov     [rsp+168h+var_138], 740h; int
0x180012f6b  lea     rax, aReadwimheader; "ReadWimHeader"
0x180012f72  mov     [rsp+168h+var_140], rax; __int64
0x180012f77  mov     [rsp+168h+Status], 8007000Bh; Status
0x180012f7f  lea     r9, aVersionHeaderM; "version/header mismatch"
0x180012f86  xor     edx, edx; int
0x180012f88  lea     ecx, [rdx+2]; int
0x180012f8b  call    _WIMLogMsg
0x180012f90  nop
0x180012f91  test    r12d, r12d
0x180012f94  jz      short loc_180012FA6
0x180012f96  mov     rcx, r14
0x180012f99  call    GetWimFileHandle
0x180012f9e  mov     rcx, rax; hFile
0x180012fa1  call    ReleaseWIMHeaderLock
0x180012fa6  test    esi, esi
0x180012fa8  jz      short loc_180012FB8
0x180012faa  mov     ecx, esi; dwErrCode
0x180012fac  call    cs:__imp_SetLastError
0x180012fb3  nop     dword ptr [rax+rax+00h]
0x180012fb8  mov     eax, r15d
0x180012fbb  mov     rcx, [rsp+168h+var_28]
0x180012fc3  xor     rcx, rsp; StackCookie
0x180012fc6  call    __security_check_cookie
0x180012fcb  lea     r11, [rsp+168h+var_18]
0x180012fd3  mov     rbx, [r11+28h]
0x180012fd7  mov     rsi, [r11+30h]
0x180012fdb  mov     rdi, [r11+38h]
0x180012fdf  mov     rsp, r11
0x180012fe2  pop     r15
0x180012fe4  pop     r14
0x180012fe6  pop     r12
0x180012fe8  retn
0x180061acb  push    rbp
0x180061acd  sub     rsp, 40h
0x180061ad1  mov     rbp, rdx
0x180061ad4  cmp     dword ptr [rbp+40h], 0
0x180061ad8  jz      short loc_180061AEC
0x180061ada  mov     rcx, [rbp+48h]
0x180061ade  call    GetWimFileHandle
0x180061ae3  mov     rcx, rax; hFile
0x180061ae6  call    ReleaseWIMHeaderLock
0x180061aeb  nop
0x180061aec  add     rsp, 40h
0x180061af0  pop     rbp
0x180061af1  retn
```
