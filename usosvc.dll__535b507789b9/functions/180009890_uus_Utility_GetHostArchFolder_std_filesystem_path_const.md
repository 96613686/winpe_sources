# uus::Utility::GetHostArchFolder(std::filesystem::path const &)

- ea: `0x180009890`
- end: `0x180009990`
- name: `?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009364`

## callees

- `0x1800026d0`
- `0x180008b08`
- `0x180008c74`
- `0x180009600`
- `0x180009890`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800098c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800098c3`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1800098d6`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1800098d6`

## pseudocode

```c
__int64 __fastcall uus::Utility::GetHostArchFolder(__int64 a1, struct std::filesystem::path *a2)
{
  HANDLE CurrentProcess; // rax
  std::filesystem *ArchFolderFromMachine; // rax
  __int64 v6; // rax
  _WORD v8[2]; // [rsp+20h] [rbp-68h] BYREF
  _WORD v9[6]; // [rsp+24h] [rbp-64h] BYREF
  __int64 v10; // [rsp+30h] [rbp-58h]
  _BYTE Src[32]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v12[32]; // [rsp+58h] [rbp-30h] BYREF

  v10 = a1;
  v9[0] = 0;
  v8[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (unsigned int)IsWow64Process2(CurrentProcess, v9, v8) && v8[0] && v8[0] != 0x8664 )
  {
    ArchFolderFromMachine = (std::filesystem *)uus::Utility::GetArchFolderFromMachine(v12, v8[0]);
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
    std::wstring::~wstring(v12);
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
0x180009890  mov     [rsp+arg_10], rbx
0x180009895  push    rdi
0x180009896  sub     rsp, 80h
0x18000989d  mov     rax, cs:__security_cookie
0x1800098a4  xor     rax, rsp
0x1800098a7  mov     [rsp+88h+var_10], rax
0x1800098ac  mov     rdi, rdx
0x1800098af  mov     rbx, rcx
0x1800098b2  mov     [rsp+88h+var_58], rcx
0x1800098b7  xor     eax, eax
0x1800098b9  mov     [rsp+88h+var_64], ax
0x1800098be  mov     [rsp+88h+var_68], ax
0x1800098c3  call    cs:__imp_GetCurrentProcess
0x1800098c9  mov     rcx, rax
0x1800098cc  lea     r8, [rsp+88h+var_68]
0x1800098d1  lea     rdx, [rsp+88h+var_64]
0x1800098d6  call    cs:__imp_IsWow64Process2
0x1800098dc  test    eax, eax
0x1800098de  jz      loc_18000996B
0x1800098e4  xor     eax, eax
0x1800098e6  movzx   ecx, [rsp+88h+var_68]
0x1800098eb  cmp     ax, cx
0x1800098ee  jz      short loc_18000996B
0x1800098f0  mov     eax, 8664h
0x1800098f5  cmp     ax, cx
0x1800098f8  jz      short loc_18000996B
0x1800098fa  mov     edx, ecx
0x1800098fc  lea     rcx, [rsp+88h+var_30]
0x180009901  call    ?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z; uus::Utility::GetArchFolderFromMachine(uint)
0x180009906  nop
0x180009907  mov     r8, rax; this
0x18000990a  mov     rdx, rdi; struct std::filesystem::path *
0x18000990d  lea     rcx, [rsp+88h+Src]; Src
0x180009912  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180009917  xorps   xmm0, xmm0
0x18000991a  movups  xmmword ptr [rbx], xmm0
0x18000991d  mov     qword ptr [rbx+10h], 0
0x180009925  mov     qword ptr [rbx+18h], 0
0x18000992d  movups  xmm0, xmmword ptr [rax]
0x180009930  movups  xmmword ptr [rbx], xmm0
0x180009933  movups  xmm1, xmmword ptr [rax+10h]
0x180009937  movups  xmmword ptr [rbx+10h], xmm1
0x18000993b  mov     qword ptr [rax+10h], 0
0x180009943  mov     qword ptr [rax+18h], 7
0x18000994b  xor     ecx, ecx
0x18000994d  mov     [rax], cx
0x180009950  mov     byte ptr [rbx+20h], 1
0x180009954  lea     rcx, [rsp+88h+Src]
0x180009959  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000995e  nop
0x18000995f  lea     rcx, [rsp+88h+var_30]
0x180009964  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009969  jmp     short loc_18000996F
0x18000996b  mov     byte ptr [rbx+20h], 0
0x18000996f  mov     rax, rbx
0x180009972  mov     rcx, [rsp+88h+var_10]
0x180009977  xor     rcx, rsp; StackCookie
0x18000997a  call    __security_check_cookie
0x18000997f  mov     rbx, [rsp+88h+arg_10]
0x180009987  add     rsp, 80h
0x18000998e  pop     rdi
0x18000998f  retn
```
