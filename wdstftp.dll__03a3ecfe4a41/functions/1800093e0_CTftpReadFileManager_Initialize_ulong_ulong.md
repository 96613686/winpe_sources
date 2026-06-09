# CTftpReadFileManager::Initialize(ulong,ulong)

- ea: `0x1800093e0`
- end: `0x1800094b3`
- name: `?Initialize@CTftpReadFileManager@@QEAAKKK@Z`
- size: `211`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800012e0`

## callees

- `0x1800093e0`
- `0x18000a4b8`
- `0x18003ce78`
- `0x18003cf50`
- `0x18003d028`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800093f7`
- `KERNEL32!EnterCriticalSection` at `0x1800093f7`
- `KERNEL32!LeaveCriticalSection` at `0x180009495`
- `KERNEL32!LeaveCriticalSection` at `0x180009495`

## string_xrefs

- `0x18000942b`: `base\eco\wds\transport\server\tftp\tftpreadfilemanager.cpp`
- `0x180009482`: `base\eco\wds\transport\server\tftp\tftpreadfilemanager.cpp`

## pseudocode

```c
__int64 __fastcall CTftpReadFileManager::Initialize(LPCRITICAL_SECTION lpCriticalSection, int a2, unsigned int a3)
{
  unsigned __int64 v3; // rdi
  int v6; // ebx
  const char *v7; // rdx
  const char *v8; // r8
  unsigned int v9; // r9d
  int v10; // eax
  const char *v11; // rdx

  v3 = a3;
  EnterCriticalSection(lpCriticalSection);
  LODWORD(lpCriticalSection[1].DebugInfo) = a2;
  if ( is_mul_ok(v3, 0x100000u) )
  {
    *(_QWORD *)&lpCriticalSection[1].LockCount = v3 << 20;
    v6 = 0;
  }
  else
  {
    *(_QWORD *)&lpCriticalSection[1].LockCount = -1;
    v6 = -2147024362;
  }
  ElValidateHrLite(
    v6,
    (const char *)((v3 * (unsigned __int128)0x100000uLL) >> 64),
    "base\\eco\\wds\\transport\\server\\tftp\\tftpreadfilemanager.cpp",
    0x6Eu);
  if ( v6 >= 0 )
    v10 = v6;
  else
    v10 = ElValidateHr(v6, v7, v8, v9);
  if ( v10 >= 0 )
  {
    v6 = CTimer<CTftpReadFileManager>::Initialize(
           &lpCriticalSection[1].LockSemaphore,
           1000 * LODWORD(lpCriticalSection[1].DebugInfo));
    ElValidateWin32(v6, v11, "base\\eco\\wds\\transport\\server\\tftp\\tftpreadfilemanager.cpp", 0x74u);
  }
  else if ( v6 < 0 )
  {
    v6 = (unsigned __int16)v6;
  }
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800093e0  mov     [rsp+arg_0], rbx
0x1800093e5  mov     [rsp+arg_8], rsi
0x1800093ea  push    rdi
0x1800093eb  sub     rsp, 40h
0x1800093ef  mov     edi, r8d
0x1800093f2  mov     ebx, edx
0x1800093f4  mov     rsi, rcx
0x1800093f7  call    cs:__imp_EnterCriticalSection
0x1800093fe  nop     dword ptr [rax+rax+00h]
0x180009403  mov     eax, 100000h
0x180009408  mov     [rsi+28h], ebx
0x18000940b  mul     rdi
0x18000940e  test    rdx, rdx
0x180009411  jnz     short loc_18000941B
0x180009413  mov     [rsi+30h], rax
0x180009417  xor     ebx, ebx
0x180009419  jmp     short loc_180009425
0x18000941b  or      qword ptr [rsi+30h], 0FFFFFFFFFFFFFFFFh
0x180009420  mov     ebx, 80070216h
0x180009425  mov     r9d, 6Eh ; 'n'; unsigned int
0x18000942b  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\tftp"...
0x180009432  mov     ecx, ebx; int
0x180009434  call    ?ElValidateHrLite@@YAJJPEBD0K@Z; ElValidateHrLite(long,char const *,char const *,ulong)
0x180009439  test    ebx, ebx
0x18000943b  jns     short loc_180009446
0x18000943d  mov     ecx, ebx; int
0x18000943f  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180009444  jmp     short loc_180009448
0x180009446  mov     eax, ebx
0x180009448  test    eax, eax
0x18000944a  jns     short loc_180009463
0x18000944c  test    ebx, ebx
0x18000944e  jns     short loc_180009492
0x180009450  mov     eax, ebx
0x180009452  and     eax, 1FFF0000h
0x180009457  cmp     eax, 70000h
0x18000945c  jnz     short loc_180009492
0x18000945e  movzx   ebx, bx
0x180009461  jmp     short loc_180009492
0x180009463  imul    r9d, [rsi+28h], 3E8h
0x18000946b  lea     rcx, [rsi+40h]; Parameter
0x18000946f  mov     rdx, rsi
0x180009472  mov     [rsp+48h+var_28], r9d; DWORD
0x180009477  call    ?Initialize@?$CTimer@VCTftpReadFileManager@@@@QEAAKPEAVCTftpReadFileManager@@PEAXKK1K@Z; CTimer<CTftpReadFileManager>::Initialize(CTftpReadFileManager *,void *,ulong,ulong,void *,ulong)
0x18000947c  mov     r9d, 74h ; 't'; unsigned int
0x180009482  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\tftp"...
0x180009489  mov     ecx, eax; unsigned int
0x18000948b  mov     ebx, eax
0x18000948d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009492  mov     rcx, rsi; lpCriticalSection
0x180009495  call    cs:__imp_LeaveCriticalSection
0x18000949c  nop     dword ptr [rax+rax+00h]
0x1800094a1  mov     rsi, [rsp+48h+arg_8]
0x1800094a6  mov     eax, ebx
0x1800094a8  mov     rbx, [rsp+48h+arg_0]
0x1800094ad  add     rsp, 40h
0x1800094b1  pop     rdi
0x1800094b2  retn
```
