# uus::Utility::GetHostArchFolder(std::filesystem::path const &)

- ea: `0x180008388`
- end: `0x18000847d`
- name: `?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z`
- size: `245`
- prototype: `__int64 __fastcall(__int64, struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008848`

## callees

- `0x180008388`
- `0x180008ebc`
- `0x1800098b8`
- `0x18000a98c`
- `0x18000fc90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800083c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800083c0`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1800083d3`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1800083d3`

## pseudocode

```c
__int64 __fastcall uus::Utility::GetHostArchFolder(__int64 a1, struct std::filesystem::path *a2)
{
  HANDLE CurrentProcess; // rax
  void *ArchFolderFromMachine; // rax
  __int64 v6; // rax
  _BYTE Src[32]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v9[32]; // [rsp+50h] [rbp-38h] BYREF
  _WORD v10[2]; // [rsp+70h] [rbp-18h] BYREF
  __int16 v11; // [rsp+74h] [rbp-14h] BYREF

  v11 = 0;
  v10[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (unsigned int)IsWow64Process2(CurrentProcess, &v11, v10) && v10[0] && v10[0] != 0x8664 )
  {
    ArchFolderFromMachine = (void *)uus::Utility::GetArchFolderFromMachine(v9, v10[0]);
    v6 = std::filesystem::operator/(Src, a2, ArchFolderFromMachine);
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)v6;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(v6 + 16);
    *(_QWORD *)(v6 + 16) = 0;
    *(_QWORD *)(v6 + 24) = 7;
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
0x180008388  mov     [rsp+arg_10], rbx
0x18000838d  mov     [rsp+arg_18], rsi
0x180008392  push    rdi
0x180008393  sub     rsp, 80h
0x18000839a  mov     rax, cs:__security_cookie
0x1800083a1  xor     rax, rsp
0x1800083a4  mov     [rsp+88h+var_10], rax
0x1800083a9  mov     rdi, rdx
0x1800083ac  mov     rbx, rcx
0x1800083af  mov     [rsp+88h+var_60], rcx
0x1800083b4  xor     esi, esi
0x1800083b6  mov     [rsp+88h+var_14], si
0x1800083bb  mov     [rsp+88h+var_18], si
0x1800083c0  call    cs:__imp_GetCurrentProcess
0x1800083c6  mov     rcx, rax
0x1800083c9  lea     r8, [rsp+88h+var_18]
0x1800083ce  lea     rdx, [rsp+88h+var_14]
0x1800083d3  call    cs:__imp_IsWow64Process2
0x1800083d9  test    eax, eax
0x1800083db  jz      short loc_180008454
0x1800083dd  movzx   eax, [rsp+88h+var_18]
0x1800083e2  cmp     si, ax
0x1800083e5  jz      short loc_180008454
0x1800083e7  mov     ecx, 8664h
0x1800083ec  cmp     cx, ax
0x1800083ef  jz      short loc_180008454
0x1800083f1  mov     edx, eax
0x1800083f3  lea     rcx, [rsp+88h+var_38]
0x1800083f8  call    ?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z; uus::Utility::GetArchFolderFromMachine(uint)
0x1800083fd  nop
0x1800083fe  mov     r8, rax; void *
0x180008401  mov     rdx, rdi; struct std::filesystem::path *
0x180008404  lea     rcx, [rsp+88h+Src]; Src
0x180008409  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18000840e  xorps   xmm0, xmm0
0x180008411  movups  xmmword ptr [rbx], xmm0
0x180008414  mov     [rbx+10h], rsi
0x180008418  mov     [rbx+18h], rsi
0x18000841c  movups  xmm0, xmmword ptr [rax]
0x18000841f  movups  xmmword ptr [rbx], xmm0
0x180008422  movups  xmm1, xmmword ptr [rax+10h]
0x180008426  movups  xmmword ptr [rbx+10h], xmm1
0x18000842a  mov     [rax+10h], rsi
0x18000842e  mov     qword ptr [rax+18h], 7
0x180008436  mov     [rax], si
0x180008439  mov     byte ptr [rbx+20h], 1
0x18000843d  lea     rcx, [rsp+88h+Src]
0x180008442  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008447  nop
0x180008448  lea     rcx, [rsp+88h+var_38]
0x18000844d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008452  jmp     short loc_180008458
0x180008454  mov     [rbx+20h], sil
0x180008458  mov     rax, rbx
0x18000845b  mov     rcx, [rsp+88h+var_10]
0x180008460  xor     rcx, rsp; StackCookie
0x180008463  call    __security_check_cookie
0x180008468  lea     r11, [rsp+88h+var_8]
0x180008470  mov     rbx, [r11+20h]
0x180008474  mov     rsi, [r11+28h]
0x180008478  mov     rsp, r11
0x18000847b  pop     rdi
0x18000847c  retn
```
