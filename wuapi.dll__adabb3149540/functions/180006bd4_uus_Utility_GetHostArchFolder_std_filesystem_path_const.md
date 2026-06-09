# uus::Utility::GetHostArchFolder(std::filesystem::path const &)

- ea: `0x180006bd4`
- end: `0x180006cc9`
- name: `?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006f90`

## callees

- `0x1800061a4`
- `0x180006a74`
- `0x180006bd4`
- `0x1800085e8`
- `0x18000fce0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006c0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006c0c`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180006c1f`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180006c1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall uus::Utility::GetHostArchFolder(__int64 a1, struct std::filesystem::path *a2)
{
  HANDLE CurrentProcess; // rax
  _QWORD *ArchFolderFromMachine; // rax
  std::filesystem::path *v6; // rax
  _BYTE Src[32]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v9[32]; // [rsp+50h] [rbp-38h] BYREF
  _WORD v10[2]; // [rsp+70h] [rbp-18h] BYREF
  __int16 v11; // [rsp+74h] [rbp-14h] BYREF

  v11 = 0;
  v10[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (unsigned int)IsWow64Process2(CurrentProcess, &v11, v10) && v10[0] && v10[0] != 0x8664 )
  {
    ArchFolderFromMachine = (_QWORD *)uus::Utility::GetArchFolderFromMachine(v9, v10[0]);
    v6 = std::filesystem::operator/((std::filesystem::path *)Src, a2, ArchFolderFromMachine);
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)v6;
    *(_OWORD *)(a1 + 16) = *((_OWORD *)v6 + 1);
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 3) = 7;
    *(_WORD *)v6 = 0;
    *(_BYTE *)(a1 + 32) = 1;
    std::wstring::~wstring(Src);
    std::wstring::~wstring(v9);
  }
  else
  {
    *(_BYTE *)(a1 + 32) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180006bd4  mov     [rsp+arg_10], rbx
0x180006bd9  mov     [rsp+arg_18], rsi
0x180006bde  push    rdi
0x180006bdf  sub     rsp, 80h
0x180006be6  mov     rax, cs:__security_cookie
0x180006bed  xor     rax, rsp
0x180006bf0  mov     [rsp+88h+var_10], rax
0x180006bf5  mov     rdi, rdx
0x180006bf8  mov     rbx, rcx
0x180006bfb  mov     [rsp+88h+var_60], rcx
0x180006c00  xor     esi, esi
0x180006c02  mov     [rsp+88h+var_14], si
0x180006c07  mov     [rsp+88h+var_18], si
0x180006c0c  call    cs:__imp_GetCurrentProcess
0x180006c12  mov     rcx, rax
0x180006c15  lea     r8, [rsp+88h+var_18]
0x180006c1a  lea     rdx, [rsp+88h+var_14]
0x180006c1f  call    cs:__imp_IsWow64Process2
0x180006c25  test    eax, eax
0x180006c27  jz      short loc_180006CA0
0x180006c29  movzx   eax, [rsp+88h+var_18]
0x180006c2e  cmp     si, ax
0x180006c31  jz      short loc_180006CA0
0x180006c33  mov     ecx, 8664h
0x180006c38  cmp     cx, ax
0x180006c3b  jz      short loc_180006CA0
0x180006c3d  mov     edx, eax
0x180006c3f  lea     rcx, [rsp+88h+var_38]
0x180006c44  call    ?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z; uus::Utility::GetArchFolderFromMachine(uint)
0x180006c49  nop
0x180006c4a  mov     r8, rax; void *
0x180006c4d  mov     rdx, rdi; struct std::filesystem::path *
0x180006c50  lea     rcx, [rsp+88h+Src]; Src
0x180006c55  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180006c5a  xorps   xmm0, xmm0
0x180006c5d  movups  xmmword ptr [rbx], xmm0
0x180006c60  mov     [rbx+10h], rsi
0x180006c64  mov     [rbx+18h], rsi
0x180006c68  movups  xmm0, xmmword ptr [rax]
0x180006c6b  movups  xmmword ptr [rbx], xmm0
0x180006c6e  movups  xmm1, xmmword ptr [rax+10h]
0x180006c72  movups  xmmword ptr [rbx+10h], xmm1
0x180006c76  mov     [rax+10h], rsi
0x180006c7a  mov     qword ptr [rax+18h], 7
0x180006c82  mov     [rax], si
0x180006c85  mov     byte ptr [rbx+20h], 1
0x180006c89  lea     rcx, [rsp+88h+Src]
0x180006c8e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006c93  nop
0x180006c94  lea     rcx, [rsp+88h+var_38]
0x180006c99  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006c9e  jmp     short loc_180006CA4
0x180006ca0  mov     [rbx+20h], sil
0x180006ca4  mov     rax, rbx
0x180006ca7  mov     rcx, [rsp+88h+var_10]
0x180006cac  xor     rcx, rsp; StackCookie
0x180006caf  call    __security_check_cookie
0x180006cb4  lea     r11, [rsp+88h+var_8]
0x180006cbc  mov     rbx, [r11+20h]
0x180006cc0  mov     rsi, [r11+28h]
0x180006cc4  mov     rsp, r11
0x180006cc7  pop     rdi
0x180006cc8  retn
```
