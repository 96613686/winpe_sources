# CSWbemDateTime::SetFileTime(ushort *,short)

- ea: `0x180017e60`
- end: `0x180018031`
- name: `?SetFileTime@CSWbemDateTime@@UEAAJPEAGF@Z`
- size: `465`
- prototype: `__int64 __fastcall(CSWbemDateTime *__hidden this, unsigned __int16 *, __int16)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callees

- `0x1800050dc`
- `0x180006300`
- `0x180017e60`
- `0x18002f6e4`
- `0x180034090`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017f20`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017f20`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180017ef9`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180017ef9`

## pseudocode

```c
__int64 __fastcall CSWbemDateTime::SetFileTime(CSWbemDateTime *this, unsigned __int16 *a2, __int16 a3)
{
  FILETIME v6; // rbx
  FILETIME v7; // rdx
  int LocalOffsetForDate; // r9d
  int v9; // r8d
  unsigned int v10; // ebx
  FILETIME FileTime; // [rsp+20h] [rbp-30h] BYREF
  struct _FILETIME v13; // [rsp+28h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-20h] BYREF

  ResetLastErrors();
  v6 = 0;
  while ( *(unsigned __int64 *)&v6 < 0x1FFFFFFFFFFFFFFFLL && (unsigned __int16)(*a2 - 48) <= 9u )
  {
    v7 = v6;
    v6 = (FILETIME)(*a2 + 2 * (5LL * *(_QWORD *)&v6 - 24));
    if ( *(_QWORD *)&v6 < *(unsigned __int64 *)&v7 )
      goto LABEL_11;
    ++a2;
  }
  if ( *a2 || (FileTime = v6, SystemTime = 0, !FileTimeToSystemTime(&FileTime, &SystemTime)) )
  {
LABEL_11:
    v10 = -2147217375;
    CDispatchHelp::RaiseException((CSWbemDateTime *)((char *)this + 32), -2147217375);
    return v10;
  }
  LocalOffsetForDate = 0;
  if ( a3 == -1 )
  {
    v13 = 0;
    SystemTimeToFileTime(&SystemTime, &v13);
    LocalOffsetForDate = CSWbemDateTime::WBEMTime::GetLocalOffsetForDate(&SystemTime);
  }
  *((_DWORD *)this + 33) = SystemTime.wYear;
  *((_DWORD *)this + 34) = SystemTime.wMonth;
  *((_DWORD *)this + 35) = SystemTime.wDay;
  *((_DWORD *)this + 36) = SystemTime.wHour;
  *((_DWORD *)this + 37) = SystemTime.wMinute;
  *((_DWORD *)this + 38) = SystemTime.wSecond;
  *((_DWORD *)this + 40) = LocalOffsetForDate;
  *((_WORD *)this + 56) = -1;
  v9 = 1000 * SystemTime.wMilliseconds;
  *((_WORD *)this + 57) = -1;
  *((_WORD *)this + 58) = -1;
  *((_WORD *)this + 59) = -1;
  *((_WORD *)this + 60) = -1;
  *((_WORD *)this + 61) = -1;
  *((_DWORD *)this + 39) = v9 + *(unsigned __int64 *)&v6 % 0x2710 / 0xA;
  *((_WORD *)this + 62) = -1;
  *((_WORD *)this + 63) = -1;
  *((_WORD *)this + 64) = 0;
  *((_DWORD *)this + 42) = *(unsigned __int64 *)&v6 % 0xA;
  return 0;
}

```

## disassembly

```asm
0x180017e60  mov     [rsp-28h+arg_10], rbx
0x180017e65  push    rbp
0x180017e66  push    rsi
0x180017e67  push    rdi
0x180017e68  push    r14
0x180017e6a  push    r15
0x180017e6c  mov     rbp, rsp
0x180017e6f  sub     rsp, 50h
0x180017e73  mov     rax, cs:__security_cookie
0x180017e7a  xor     rax, rsp
0x180017e7d  mov     [rbp+var_10], rax
0x180017e81  movzx   r14d, r8w
0x180017e85  mov     rdi, rdx
0x180017e88  mov     rsi, rcx
0x180017e8b  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x180017e90  xor     r15d, r15d
0x180017e93  mov     ebx, r15d
0x180017e96  mov     rax, 1FFFFFFFFFFFFFFFh
0x180017ea0  cmp     rbx, rax
0x180017ea3  jnb     short loc_180017ED3
0x180017ea5  movzx   eax, word ptr [rdi]
0x180017ea8  sub     ax, 30h ; '0'
0x180017eac  cmp     ax, 9
0x180017eb0  ja      short loc_180017ED3
0x180017eb2  movzx   eax, word ptr [rdi]
0x180017eb5  mov     rdx, rbx
0x180017eb8  lea     rbx, [rbx+rbx*4]
0x180017ebc  lea     rbx, [rbx-18h]
0x180017ec0  lea     rbx, [rax+rbx*2]
0x180017ec4  cmp     rbx, rdx
0x180017ec7  jb      loc_180017FFF
0x180017ecd  add     rdi, 2
0x180017ed1  jmp     short loc_180017E96
0x180017ed3  cmp     [rdi], r15w
0x180017ed7  jnz     loc_180017FFF
0x180017edd  xorps   xmm0, xmm0
0x180017ee0  mov     [rbp+FileTime.dwLowDateTime], ebx
0x180017ee3  mov     rax, rbx
0x180017ee6  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180017eea  shr     rax, 20h
0x180017eee  lea     rcx, [rbp+FileTime]; lpFileTime
0x180017ef2  mov     [rbp+FileTime.dwHighDateTime], eax
0x180017ef5  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180017ef9  call    cs:__imp_FileTimeToSystemTime
0x180017eff  cmp     eax, 1
0x180017f02  jnz     loc_180017FFF
0x180017f08  or      edi, 0FFFFFFFFh
0x180017f0b  mov     r9d, r15d
0x180017f0e  cmp     di, r14w
0x180017f12  jnz     short loc_180017F32
0x180017f14  lea     rdx, [rbp+var_28]; lpFileTime
0x180017f18  mov     qword ptr [rbp+var_28.dwLowDateTime], r15
0x180017f1c  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180017f20  call    cs:__imp_SystemTimeToFileTime
0x180017f26  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180017f2a  call    ?GetLocalOffsetForDate@WBEMTime@CSWbemDateTime@@SAJPEBU_SYSTEMTIME@@@Z; CSWbemDateTime::WBEMTime::GetLocalOffsetForDate(_SYSTEMTIME const *)
0x180017f2f  mov     r9d, eax
0x180017f32  movzx   ecx, [rbp+SystemTime.wYear]
0x180017f36  mov     r10, 0CCCCCCCCCCCCCCCDh
0x180017f40  mov     [rsi+84h], ecx
0x180017f46  mov     rax, 346DC5D63886594Bh
0x180017f50  movzx   ecx, [rbp+SystemTime.wMonth]
0x180017f54  mul     rbx
0x180017f57  mov     [rsi+88h], ecx
0x180017f5d  movzx   ecx, [rbp+SystemTime.wDay]
0x180017f61  shr     rdx, 0Bh
0x180017f65  imul    rax, rdx, 2710h
0x180017f6c  mov     [rsi+8Ch], ecx
0x180017f72  movzx   ecx, [rbp+SystemTime.wHour]
0x180017f76  mov     [rsi+90h], ecx
0x180017f7c  movzx   ecx, [rbp+SystemTime.wMinute]
0x180017f80  mov     [rsi+94h], ecx
0x180017f86  movzx   ecx, [rbp+SystemTime.wSecond]
0x180017f8a  mov     [rsi+98h], ecx
0x180017f90  mov     rcx, rbx
0x180017f93  sub     rcx, rax
0x180017f96  mov     [rsi+0A0h], r9d
0x180017f9d  mov     rax, r10
0x180017fa0  mov     [rsi+70h], di
0x180017fa4  mul     rcx
0x180017fa7  movzx   ecx, [rbp+SystemTime.wMilliseconds]
0x180017fab  mov     rax, r10
0x180017fae  shr     rdx, 3
0x180017fb2  imul    r8d, ecx, 3E8h
0x180017fb9  mov     [rsi+72h], di
0x180017fbd  mov     [rsi+74h], di
0x180017fc1  mov     [rsi+76h], di
0x180017fc5  mov     [rsi+78h], di
0x180017fc9  add     edx, r8d
0x180017fcc  mov     [rsi+7Ah], di
0x180017fd0  mov     [rsi+9Ch], edx
0x180017fd6  mul     rbx
0x180017fd9  mov     [rsi+7Ch], di
0x180017fdd  shr     rdx, 3
0x180017fe1  mov     [rsi+7Eh], di
0x180017fe5  mov     [rsi+80h], r15w
0x180017fed  lea     eax, [rdx+rdx*4]
0x180017ff0  add     eax, eax
0x180017ff2  sub     ebx, eax
0x180017ff4  mov     [rsi+0A8h], ebx
0x180017ffa  mov     ebx, r15d
0x180017ffd  jmp     short loc_18001800F
0x180017fff  mov     ebx, 80041021h
0x180018004  lea     rcx, [rsi+20h]; this
0x180018008  mov     edx, ebx; int
0x18001800a  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18001800f  mov     eax, ebx
0x180018011  mov     rcx, [rbp+var_10]
0x180018015  xor     rcx, rsp; StackCookie
0x180018018  call    __security_check_cookie
0x18001801d  mov     rbx, [rsp+50h+arg_10]
0x180018025  add     rsp, 50h
0x180018029  pop     r15
0x18001802b  pop     r14
0x18001802d  pop     rdi
0x18001802e  pop     rsi
0x18001802f  pop     rbp
0x180018030  retn
```
