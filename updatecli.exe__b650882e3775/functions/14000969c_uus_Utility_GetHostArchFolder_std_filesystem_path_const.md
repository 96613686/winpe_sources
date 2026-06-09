# uus::Utility::GetHostArchFolder(std::filesystem::path const &)

- ea: `0x14000969c`
- end: `0x14000979c`
- name: `?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400091e4`

## callees

- `0x140002130`
- `0x1400087c4`
- `0x140008a34`
- `0x14000953c`
- `0x14000969c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400096cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400096cf`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1400096e2`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1400096e2`

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
0x14000969c  mov     [rsp+arg_10], rbx
0x1400096a1  push    rdi
0x1400096a2  sub     rsp, 80h
0x1400096a9  mov     rax, cs:__security_cookie
0x1400096b0  xor     rax, rsp
0x1400096b3  mov     [rsp+88h+var_10], rax
0x1400096b8  mov     rdi, rdx
0x1400096bb  mov     rbx, rcx
0x1400096be  mov     [rsp+88h+var_58], rcx
0x1400096c3  xor     eax, eax
0x1400096c5  mov     [rsp+88h+var_64], ax
0x1400096ca  mov     [rsp+88h+var_68], ax
0x1400096cf  call    cs:__imp_GetCurrentProcess
0x1400096d5  mov     rcx, rax
0x1400096d8  lea     r8, [rsp+88h+var_68]
0x1400096dd  lea     rdx, [rsp+88h+var_64]
0x1400096e2  call    cs:__imp_IsWow64Process2
0x1400096e8  test    eax, eax
0x1400096ea  jz      loc_140009777
0x1400096f0  xor     eax, eax
0x1400096f2  movzx   ecx, [rsp+88h+var_68]
0x1400096f7  cmp     ax, cx
0x1400096fa  jz      short loc_140009777
0x1400096fc  mov     eax, 8664h
0x140009701  cmp     ax, cx
0x140009704  jz      short loc_140009777
0x140009706  mov     edx, ecx
0x140009708  lea     rcx, [rsp+88h+var_30]
0x14000970d  call    ?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z; uus::Utility::GetArchFolderFromMachine(uint)
0x140009712  nop
0x140009713  mov     r8, rax; this
0x140009716  mov     rdx, rdi; struct std::filesystem::path *
0x140009719  lea     rcx, [rsp+88h+Src]; Src
0x14000971e  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x140009723  xorps   xmm0, xmm0
0x140009726  movups  xmmword ptr [rbx], xmm0
0x140009729  mov     qword ptr [rbx+10h], 0
0x140009731  mov     qword ptr [rbx+18h], 0
0x140009739  movups  xmm0, xmmword ptr [rax]
0x14000973c  movups  xmmword ptr [rbx], xmm0
0x14000973f  movups  xmm1, xmmword ptr [rax+10h]
0x140009743  movups  xmmword ptr [rbx+10h], xmm1
0x140009747  mov     qword ptr [rax+10h], 0
0x14000974f  mov     qword ptr [rax+18h], 7
0x140009757  xor     ecx, ecx
0x140009759  mov     [rax], cx
0x14000975c  mov     byte ptr [rbx+20h], 1
0x140009760  lea     rcx, [rsp+88h+Src]
0x140009765  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000976a  nop
0x14000976b  lea     rcx, [rsp+88h+var_30]
0x140009770  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009775  jmp     short loc_14000977B
0x140009777  mov     byte ptr [rbx+20h], 0
0x14000977b  mov     rax, rbx
0x14000977e  mov     rcx, [rsp+88h+var_10]
0x140009783  xor     rcx, rsp; StackCookie
0x140009786  call    __security_check_cookie
0x14000978b  mov     rbx, [rsp+88h+arg_10]
0x140009793  add     rsp, 80h
0x14000979a  pop     rdi
0x14000979b  retn
```
