# CTrace::Initialize(ushort const *,int)

- ea: `0x180010ec0`
- end: `0x180011059`
- name: `?Initialize@CTrace@@QEAAKPEBGH@Z`
- size: `409`
- prototype: `unsigned int(CTrace *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x180006310`
- `0x180010ec0`
- `0x180011c88`
- `0x180011d84`
- `0x180011f74`
- `0x1800172b0`
- `0x180030362`
- `0x180030390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010fa0`
- `KERNEL32!GetLastError` at `0x180010fcb`
- `KERNEL32!GetLastError` at `0x180010fef`
- `KERNEL32!GetLastError` at `0x180010fa0`
- `KERNEL32!GetLastError` at `0x180010fcb`
- `KERNEL32!GetLastError` at `0x180010fef`
- `KERNEL32!GetCurrentProcessId` at `0x180010f24`
- `KERNEL32!GetCurrentProcessId` at `0x180010f24`
- `KERNEL32!GetEnvironmentVariableW` at `0x180010f90`
- `KERNEL32!GetEnvironmentVariableW` at `0x180010f90`
- `KERNEL32!SetEnvironmentVariableW` at `0x180010fbb`
- `KERNEL32!SetEnvironmentVariableW` at `0x180010fbb`

## pseudocode

```c
__int64 __fastcall CTrace::Initialize(CTrace *this, WCHAR *p_Buffer)
{
  unsigned int v4; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned __int16 *v13; // rax
  WCHAR Name[264]; // [rsp+20h] [rbp-448h] BYREF
  WCHAR Buffer; // [rsp+230h] [rbp-238h] BYREF
  _BYTE v17[526]; // [rsp+232h] [rbp-236h] BYREF

  Name[0] = 0;
  v4 = 0;
  memset_0(&Name[1], 0, 0x206u);
  Buffer = 0;
  memset_0(v17, 0, 0x206u);
  CurrentProcessId = GetCurrentProcessId();
  v6 = (unsigned int)StringCchPrintfW(Name, 0x104u, L"WDS_TRACING_%u", CurrentProcessId);
  if ( (int)ElValidateHr_2(v6, v7, v8, 222, *(_DWORD *)Name) < 0 )
  {
    if ( (int)v6 < 0 && (v6 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v6;
    else
      return (unsigned int)v6;
  }
  if ( GetEnvironmentVariableW(Name, &Buffer, 0x104u) )
  {
    p_Buffer = &Buffer;
  }
  else
  {
    if ( GetLastError() != 203 )
    {
      LastError = GetLastError();
      v12 = 242;
LABEL_10:
      v4 = ElValidateWin32_3(LastError, v10, v11, v12);
      if ( !v4 )
        return 31;
      return v4;
    }
    if ( !SetEnvironmentVariableW(Name, p_Buffer) )
    {
      LastError = GetLastError();
      v12 = 237;
      goto LABEL_10;
    }
  }
  v13 = WcsDup(p_Buffer);
  *(_QWORD *)this = v13;
  if ( v13 )
  {
    if ( qword_18004BE60 )
      McGenEventRegister_s_pfnEventRegister();
  }
  else
  {
    return 8;
  }
  return v4;
}

```

## disassembly

```asm
0x180010ec0  mov     [rsp+arg_10], rbx
0x180010ec5  mov     [rsp+arg_18], rbp
0x180010eca  push    rsi
0x180010ecb  push    rdi
0x180010ecc  push    r14
0x180010ece  sub     rsp, 450h
0x180010ed5  mov     rax, cs:__security_cookie
0x180010edc  xor     rax, rsp
0x180010edf  mov     [rsp+468h+var_28], rax
0x180010ee7  mov     rsi, rdx
0x180010eea  mov     r14, rcx
0x180010eed  xor     ebp, ebp
0x180010eef  lea     rcx, [rsp+468h+var_446]; void *
0x180010ef4  mov     edi, 206h
0x180010ef9  mov     [rsp+468h+Name], bp
0x180010efe  mov     r8d, edi; Size
0x180010f01  xor     edx, edx; Val
0x180010f03  mov     ebx, ebp
0x180010f05  call    memset_0
0x180010f0a  mov     r8d, edi; Size
0x180010f0d  mov     [rsp+468h+Buffer], bp
0x180010f15  xor     edx, edx; Val
0x180010f17  lea     rcx, [rsp+468h+var_236]; void *
0x180010f1f  call    memset_0
0x180010f24  call    cs:__imp_GetCurrentProcessId
0x180010f2b  nop     dword ptr [rax+rax+00h]
0x180010f30  lea     r8, aWdsTracingU; "WDS_TRACING_%u"
0x180010f37  mov     edx, 104h; unsigned __int64
0x180010f3c  mov     r9d, eax
0x180010f3f  lea     rcx, [rsp+468h+Name]; unsigned __int16 *
0x180010f44  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010f49  mov     r9d, 0DEh
0x180010f4f  mov     ecx, eax
0x180010f51  mov     edi, eax
0x180010f53  call    ElValidateHr_2
0x180010f58  test    eax, eax
0x180010f5a  jns     short loc_180010F7D
0x180010f5c  test    edi, edi
0x180010f5e  jns     short loc_180010F76
0x180010f60  mov     eax, edi
0x180010f62  and     eax, 1FFF0000h
0x180010f67  cmp     eax, 70000h
0x180010f6c  jnz     short loc_180010F76
0x180010f6e  movzx   ebx, di
0x180010f71  jmp     loc_18001102E
0x180010f76  mov     ebx, edi
0x180010f78  jmp     loc_18001102E
0x180010f7d  mov     r8d, 104h; nSize
0x180010f83  lea     rdx, [rsp+468h+Buffer]; lpBuffer
0x180010f8b  lea     rcx, [rsp+468h+Name]; lpName
0x180010f90  call    cs:__imp_GetEnvironmentVariableW
0x180010f97  nop     dword ptr [rax+rax+00h]
0x180010f9c  test    eax, eax
0x180010f9e  jnz     short loc_180011003
0x180010fa0  call    cs:__imp_GetLastError
0x180010fa7  nop     dword ptr [rax+rax+00h]
0x180010fac  cmp     eax, 0CBh
0x180010fb1  jnz     short loc_180010FEF
0x180010fb3  mov     rdx, rsi; lpValue
0x180010fb6  lea     rcx, [rsp+468h+Name]; lpName
0x180010fbb  call    cs:__imp_SetEnvironmentVariableW
0x180010fc2  nop     dword ptr [rax+rax+00h]
0x180010fc7  test    eax, eax
0x180010fc9  jnz     short loc_18001100B
0x180010fcb  call    cs:__imp_GetLastError
0x180010fd2  nop     dword ptr [rax+rax+00h]
0x180010fd7  mov     r9d, 0EDh
0x180010fdd  mov     ecx, eax
0x180010fdf  call    ElValidateWin32_3
0x180010fe4  mov     ebx, eax
0x180010fe6  test    eax, eax
0x180010fe8  jnz     short loc_18001102E
0x180010fea  lea     ebx, [rax+1Fh]
0x180010fed  jmp     short loc_18001102E
0x180010fef  call    cs:__imp_GetLastError
0x180010ff6  nop     dword ptr [rax+rax+00h]
0x180010ffb  mov     r9d, 0F2h
0x180011001  jmp     short loc_180010FDD
0x180011003  lea     rsi, [rsp+468h+Buffer]
0x18001100b  mov     rcx, rsi; Src
0x18001100e  call    ?WcsDup@@YAPEAGPEBG@Z; WcsDup(ushort const *)
0x180011013  mov     [r14], rax
0x180011016  test    rax, rax
0x180011019  jnz     short loc_180011020
0x18001101b  lea     ebx, [rax+8]
0x18001101e  jmp     short loc_18001102E
0x180011020  cmp     cs:qword_18004BE60, rbp
0x180011027  jz      short loc_18001102E
0x180011029  call    McGenEventRegister_s_pfnEventRegister
0x18001102e  mov     eax, ebx
0x180011030  mov     rcx, [rsp+468h+var_28]
0x180011038  xor     rcx, rsp; StackCookie
0x18001103b  call    __security_check_cookie
0x180011040  lea     r11, [rsp+468h+var_18]
0x180011048  mov     rbx, [r11+30h]
0x18001104c  mov     rbp, [r11+38h]
0x180011050  mov     rsp, r11
0x180011053  pop     r14
0x180011055  pop     rdi
0x180011056  pop     rsi
0x180011057  retn
```
