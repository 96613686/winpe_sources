# uus::Utility::GetHostArchFolder(std::filesystem::path const &)

- ea: `0x14000966c`
- end: `0x14000976c`
- name: `?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400091b4`

## callees

- `0x140002120`
- `0x1400087e4`
- `0x140008a04`
- `0x14000950c`
- `0x14000966c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000969f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000969f`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1400096b2`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1400096b2`

## pseudocode

```c
__int64 __fastcall uus::Utility::GetHostArchFolder(__int64 a1, struct std::filesystem::path *a2)
{
  HANDLE CurrentProcess; // rax
  std::filesystem *ArchFolderFromMachine; // rax
  std::filesystem::path *v6; // rax
  _WORD v8[2]; // [rsp+20h] [rbp-68h] BYREF
  _WORD v9[6]; // [rsp+24h] [rbp-64h] BYREF
  __int64 v10; // [rsp+30h] [rbp-58h]
  char *Src[4]; // [rsp+38h] [rbp-50h] BYREF
  char *v12[4]; // [rsp+58h] [rbp-30h] BYREF

  v10 = a1;
  v9[0] = 0;
  v8[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (unsigned int)IsWow64Process2(CurrentProcess, v9, v8) && v8[0] && v8[0] != 0x8664 )
  {
    ArchFolderFromMachine = (std::filesystem *)uus::Utility::GetArchFolderFromMachine(v12, v8[0]);
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
0x14000966c  mov     [rsp+arg_10], rbx
0x140009671  push    rdi
0x140009672  sub     rsp, 80h
0x140009679  mov     rax, cs:__security_cookie
0x140009680  xor     rax, rsp
0x140009683  mov     [rsp+88h+var_10], rax
0x140009688  mov     rdi, rdx
0x14000968b  mov     rbx, rcx
0x14000968e  mov     [rsp+88h+var_58], rcx
0x140009693  xor     eax, eax
0x140009695  mov     [rsp+88h+var_64], ax
0x14000969a  mov     [rsp+88h+var_68], ax
0x14000969f  call    cs:__imp_GetCurrentProcess
0x1400096a5  mov     rcx, rax
0x1400096a8  lea     r8, [rsp+88h+var_68]
0x1400096ad  lea     rdx, [rsp+88h+var_64]
0x1400096b2  call    cs:__imp_IsWow64Process2
0x1400096b8  test    eax, eax
0x1400096ba  jz      loc_140009747
0x1400096c0  xor     eax, eax
0x1400096c2  movzx   ecx, [rsp+88h+var_68]
0x1400096c7  cmp     ax, cx
0x1400096ca  jz      short loc_140009747
0x1400096cc  mov     eax, 8664h
0x1400096d1  cmp     ax, cx
0x1400096d4  jz      short loc_140009747
0x1400096d6  mov     edx, ecx
0x1400096d8  lea     rcx, [rsp+88h+var_30]
0x1400096dd  call    ?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z; uus::Utility::GetArchFolderFromMachine(uint)
0x1400096e2  nop
0x1400096e3  mov     r8, rax; this
0x1400096e6  mov     rdx, rdi; struct std::filesystem::path *
0x1400096e9  lea     rcx, [rsp+88h+Src]; Src
0x1400096ee  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1400096f3  xorps   xmm0, xmm0
0x1400096f6  movups  xmmword ptr [rbx], xmm0
0x1400096f9  mov     qword ptr [rbx+10h], 0
0x140009701  mov     qword ptr [rbx+18h], 0
0x140009709  movups  xmm0, xmmword ptr [rax]
0x14000970c  movups  xmmword ptr [rbx], xmm0
0x14000970f  movups  xmm1, xmmword ptr [rax+10h]
0x140009713  movups  xmmword ptr [rbx+10h], xmm1
0x140009717  mov     qword ptr [rax+10h], 0
0x14000971f  mov     qword ptr [rax+18h], 7
0x140009727  xor     ecx, ecx
0x140009729  mov     [rax], cx
0x14000972c  mov     byte ptr [rbx+20h], 1
0x140009730  lea     rcx, [rsp+88h+Src]
0x140009735  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000973a  nop
0x14000973b  lea     rcx, [rsp+88h+var_30]
0x140009740  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009745  jmp     short loc_14000974B
0x140009747  mov     byte ptr [rbx+20h], 0
0x14000974b  mov     rax, rbx
0x14000974e  mov     rcx, [rsp+88h+var_10]
0x140009753  xor     rcx, rsp; StackCookie
0x140009756  call    __security_check_cookie
0x14000975b  mov     rbx, [rsp+88h+arg_10]
0x140009763  add     rsp, 80h
0x14000976a  pop     rdi
0x14000976b  retn
```
