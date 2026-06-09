# CSdAltStreamIter::_OpenParentFile(ushort const *)

- ea: `0x180036f24`
- end: `0x1800371dd`
- name: `?_OpenParentFile@CSdAltStreamIter@@AEAAJPEBG@Z`
- size: `697`
- prototype: `int(CSdAltStreamIter *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180033870`

## callees

- `0x1800083a0`
- `0x180014c30`
- `0x180036f24`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x180093698`
- `0x18009e904`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180037028`
- `ntdll!NtQueryInformationFile` at `0x1800370b3`
- `ntdll!NtQueryInformationFile` at `0x180037028`
- `ntdll!NtQueryInformationFile` at `0x1800370b3`
- `KERNEL32!CreateFileW` at `0x180036fc7`
- `KERNEL32!CreateFileW` at `0x180036fc7`
- `KERNEL32!CloseHandle` at `0x180036fe4`
- `KERNEL32!CloseHandle` at `0x180036fe4`
- `ole32!CoTaskMemFree` at `0x18003705b`
- `ole32!CoTaskMemFree` at `0x18003705b`
- `ole32!CoTaskMemAlloc` at `0x180037078`
- `ole32!CoTaskMemAlloc` at `0x180037078`

## string_xrefs

- `0x180036f4d`: `CSdAltStreamIter::_OpenParentFile`

## pseudocode

```c
__int64 __fastcall CSdAltStreamIter::_OpenParentFile(CSdAltStreamIter *this, const unsigned __int16 *a2)
{
  __int16 v4; // ax
  LPCWSTR *v5; // r14
  int LastFailureAsHRESULT; // ebx
  HANDLE FileW; // rbx
  char *v8; // rcx
  NTSTATUS i; // eax
  unsigned int v10; // esi
  ULONG v11; // ebx
  void *v12; // rax
  __int16 v13; // ax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-29h] BYREF
  int v16; // [rsp+50h] [rbp-19h] BYREF
  __int16 v17; // [rsp+54h] [rbp-15h]
  __int16 v18; // [rsp+56h] [rbp-13h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "CSdAltStreamIter::_OpenParentFile", 0x544u, 1u);
  IoStatusBlock = 0;
  v4 = 1353;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    v16 = -2147024809;
    goto LABEL_31;
  }
  v16 = 0;
  v17 = 1353;
  v5 = (LPCWSTR *)((char *)this + 48);
  LastFailureAsHRESULT = CBsString::Set((CSdAltStreamIter *)((char *)this + 48), a2);
  v16 = LastFailureAsHRESULT;
  v4 = 1355;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_31:
    v18 = v4;
    goto LABEL_32;
  }
  v17 = 1355;
  FileW = CreateFileW(*v5, 0, 7u, 0, 3u, 0x2000000u, 0);
  v8 = (char *)*((_QWORD *)this + 5);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  *((_QWORD *)this + 5) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
    v16 = LastFailureAsHRESULT;
    v4 = 1359;
    goto LABEL_31;
  }
  v16 = 0;
  v17 = 1359;
  for ( i = NtQueryInformationFile(
              FileW,
              &IoStatusBlock,
              *((PVOID *)this + 9),
              *((_DWORD *)this + 20),
              FileStreamInformation);
        ;
        i = NtQueryInformationFile(*((HANDLE *)this + 5), &IoStatusBlock, v12, v11, FileStreamInformation) )
  {
    v10 = i;
    if ( i != -2147483643 && i != -1073741789 && i != -1073741820 )
      break;
    v11 = 2 * *((_DWORD *)this + 20);
    CoTaskMemFree(*((LPVOID *)this + 9));
    *((_QWORD *)this + 9) = 0;
    *((_DWORD *)this + 20) = 0;
    v12 = CoTaskMemAlloc(v11);
    *((_QWORD *)this + 9) = v12;
    if ( !v12 )
    {
      LastFailureAsHRESULT = -2147024882;
      v16 = -2147024882;
      v18 = 1372;
      goto LABEL_32;
    }
    v16 = 0;
    v17 = 1372;
    *((_DWORD *)this + 20) = v11;
  }
  if ( i < 0 )
  {
    if ( (unsigned int)HRESULTFromNTSTATUS((unsigned int)i) == -2147024809 )
    {
      v13 = 1384;
LABEL_15:
      LastFailureAsHRESULT = 0;
      v16 = 0;
      *((_DWORD *)this + 21) = 0;
      v17 = v13;
      goto LABEL_32;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (unsigned int)WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids,
        (unsigned int)*v5,
        v10);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v10);
    v16 = LastFailureAsHRESULT;
    v4 = 1389;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v17 = 1389;
      goto LABEL_22;
    }
    goto LABEL_31;
  }
  LastFailureAsHRESULT = v16;
LABEL_22:
  if ( IoStatusBlock.Information < 0x20 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids, v10);
    v13 = 1401;
    goto LABEL_15;
  }
  *((_DWORD *)this + 21) = 1;
  *((_QWORD *)this + 8) = *((_QWORD *)this + 9);
LABEL_32:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180036f24  push    rbp
0x180036f26  push    rbx
0x180036f27  push    rsi
0x180036f28  push    rdi
0x180036f29  push    r12
0x180036f2b  push    r13
0x180036f2d  push    r14
0x180036f2f  lea     rbp, [rsp-27h]
0x180036f34  sub     rsp, 90h
0x180036f3b  mov     rbx, rdx
0x180036f3e  mov     rdi, rcx
0x180036f41  mov     r9d, 1; unsigned __int16
0x180036f47  mov     r8d, 544h; unsigned __int16
0x180036f4d  lea     rdx, aCsdaltstreamit_2; "CSdAltStreamIter::_OpenParentFile"
0x180036f54  lea     rcx, [rbp+57h+var_70]; this
0x180036f58  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180036f5d  xorps   xmm0, xmm0
0x180036f60  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180036f64  mov     eax, 549h
0x180036f69  test    rbx, rbx
0x180036f6c  jz      loc_1800371B3
0x180036f72  mov     [rbp+57h+var_70], 0
0x180036f79  mov     [rbp+57h+var_6C], ax
0x180036f7d  lea     r14, [rdi+30h]
0x180036f81  mov     rdx, rbx; unsigned __int16 *
0x180036f84  mov     rcx, r14; this
0x180036f87  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180036f8c  mov     ebx, eax
0x180036f8e  mov     [rbp+57h+var_70], eax
0x180036f91  test    eax, eax
0x180036f93  mov     eax, 54Bh
0x180036f98  js      loc_1800371BB
0x180036f9e  mov     [rbp+57h+var_6C], ax
0x180036fa2  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x180036fab  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180036fb3  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180036fbb  xor     r9d, r9d; lpSecurityAttributes
0x180036fbe  xor     edx, edx; dwDesiredAccess
0x180036fc0  lea     r8d, [r9+7]; dwShareMode
0x180036fc4  mov     rcx, [r14]; lpFileName
0x180036fc7  call    cs:__imp_CreateFileW
0x180036fce  nop     dword ptr [rax+rax+00h]
0x180036fd3  mov     rbx, rax
0x180036fd6  mov     rcx, [rdi+28h]; hObject
0x180036fda  lea     rdx, [rcx-1]
0x180036fde  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180036fe2  ja      short loc_180036FF0
0x180036fe4  call    cs:__imp_CloseHandle
0x180036feb  nop     dword ptr [rax+rax+00h]
0x180036ff0  mov     [rdi+28h], rbx
0x180036ff4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180036ff8  jz      loc_1800371A2
0x180036ffe  mov     [rbp+57h+var_70], 0
0x180037005  mov     eax, 54Fh
0x18003700a  mov     [rbp+57h+var_6C], ax
0x18003700e  mov     r13d, 16h
0x180037014  mov     [rsp+0C0h+dwCreationDisposition], r13d; FileInformationClass
0x180037019  mov     r9d, [rdi+50h]; Length
0x18003701d  mov     r8, [rdi+48h]; FileInformation
0x180037021  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180037025  mov     rcx, rbx; FileHandle
0x180037028  call    cs:__imp_NtQueryInformationFile
0x18003702f  nop     dword ptr [rax+rax+00h]
0x180037034  mov     r12d, 55Ch
0x18003703a  mov     esi, eax
0x18003703c  cmp     eax, 80000005h
0x180037041  jz      short loc_180037051
0x180037043  cmp     eax, 0C0000023h
0x180037048  jz      short loc_180037051
0x18003704a  cmp     eax, 0C0000004h
0x18003704f  jnz     short loc_1800370C4
0x180037051  mov     eax, [rdi+50h]
0x180037054  lea     ebx, [rax+rax]
0x180037057  mov     rcx, [rdi+48h]; pv
0x18003705b  call    cs:__imp_CoTaskMemFree
0x180037062  nop     dword ptr [rax+rax+00h]
0x180037067  mov     qword ptr [rdi+48h], 0
0x18003706f  mov     dword ptr [rdi+50h], 0
0x180037076  mov     ecx, ebx; cb
0x180037078  call    cs:__imp_CoTaskMemAlloc
0x18003707f  nop     dword ptr [rax+rax+00h]
0x180037084  mov     [rdi+48h], rax
0x180037088  test    rax, rax
0x18003708b  jz      loc_180037193
0x180037091  mov     [rbp+57h+var_70], 0
0x180037098  mov     [rbp+57h+var_6C], r12w
0x18003709d  mov     [rdi+50h], ebx
0x1800370a0  mov     [rsp+0C0h+dwCreationDisposition], r13d; FileInformationClass
0x1800370a5  mov     r9d, ebx; Length
0x1800370a8  mov     r8, rax; FileInformation
0x1800370ab  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800370af  mov     rcx, [rdi+28h]; FileHandle
0x1800370b3  call    cs:__imp_NtQueryInformationFile
0x1800370ba  nop     dword ptr [rax+rax+00h]
0x1800370bf  jmp     loc_18003703A
0x1800370c4  lea     r13, WPP_GLOBAL_Control
0x1800370cb  mov     r12d, 1000h
0x1800370d1  test    esi, esi
0x1800370d3  jns     short loc_180037144
0x1800370d5  mov     ecx, esi
0x1800370d7  call    HRESULTFromNTSTATUS
0x1800370dc  mov     ebx, 80070057h
0x1800370e1  cmp     eax, ebx
0x1800370e3  jnz     short loc_1800370FB
0x1800370e5  mov     eax, 568h
0x1800370ea  xor     ebx, ebx
0x1800370ec  mov     [rbp+57h+var_70], ebx
0x1800370ef  mov     [rdi+54h], ebx
0x1800370f2  mov     [rbp+57h+var_6C], ax
0x1800370f6  jmp     loc_1800371BF
0x1800370fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180037102  cmp     rcx, r13
0x180037105  jz      short loc_180037129
0x180037107  test    [rcx+1Ch], r12d
0x18003710b  jz      short loc_180037129
0x18003710d  mov     edx, 1Eh
0x180037112  mov     [rsp+0C0h+dwCreationDisposition], esi
0x180037116  mov     r9, [r14]
0x180037119  lea     r8, WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids
0x180037120  mov     rcx, [rcx+10h]
0x180037124  call    WPP_SF_Sd
0x180037129  mov     ecx, esi
0x18003712b  call    HRESULTFromNTSTATUS
0x180037130  mov     ebx, eax
0x180037132  mov     [rbp+57h+var_70], eax
0x180037135  test    eax, eax
0x180037137  mov     eax, 56Dh
0x18003713c  js      short loc_1800371BB
0x18003713e  mov     [rbp+57h+var_6C], ax
0x180037142  jmp     short loc_180037147
0x180037144  mov     ebx, [rbp+57h+var_70]
0x180037147  cmp     [rbp+57h+IoStatusBlock.Information], 20h ; ' '
0x18003714c  jnb     short loc_180037182
0x18003714e  mov     rcx, cs:WPP_GLOBAL_Control
0x180037155  cmp     rcx, r13
0x180037158  jz      short loc_180037178
0x18003715a  test    [rcx+1Ch], r12d
0x18003715e  jz      short loc_180037178
0x180037160  mov     edx, 1Fh
0x180037165  mov     r9d, esi
0x180037168  lea     r8, WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids
0x18003716f  mov     rcx, [rcx+10h]
0x180037173  call    WPP_SF_d
0x180037178  mov     eax, 579h
0x18003717d  jmp     loc_1800370EA
0x180037182  mov     dword ptr [rdi+54h], 1
0x180037189  mov     rax, [rdi+48h]
0x18003718d  mov     [rdi+40h], rax
0x180037191  jmp     short loc_1800371BF
0x180037193  mov     ebx, 8007000Eh
0x180037198  mov     [rbp+57h+var_70], ebx
0x18003719b  mov     [rbp+57h+var_6A], r12w
0x1800371a0  jmp     short loc_1800371BF
0x1800371a2  call    GetLastFailureAsHRESULT
0x1800371a7  mov     ebx, eax
0x1800371a9  mov     [rbp+57h+var_70], eax
0x1800371ac  mov     eax, 54Fh
0x1800371b1  jmp     short loc_1800371BB
0x1800371b3  mov     ebx, 80070057h
0x1800371b8  mov     [rbp+57h+var_70], ebx
0x1800371bb  mov     [rbp+57h+var_6A], ax
0x1800371bf  lea     rcx, [rbp+57h+var_70]; this
0x1800371c3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800371c8  mov     eax, ebx
0x1800371ca  add     rsp, 90h
0x1800371d1  pop     r14
0x1800371d3  pop     r13
0x1800371d5  pop     r12
0x1800371d7  pop     rdi
0x1800371d8  pop     rsi
0x1800371d9  pop     rbx
0x1800371da  pop     rbp
0x1800371db  retn
```
