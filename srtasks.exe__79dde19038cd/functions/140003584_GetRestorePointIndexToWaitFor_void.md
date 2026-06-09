# GetRestorePointIndexToWaitFor(void)

- ea: `0x140003584`
- end: `0x140003724`
- name: `?GetRestorePointIndexToWaitFor@@YAKXZ`
- size: `416`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000312c`

## callees

- `0x140002e1c`
- `0x140003584`
- `0x140005444`
- `0x1400054f4`
- `0x14000e324`
- `0x14000e41c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140003705`
- `KERNEL32!LocalFree` at `0x140003705`
- `KERNEL32!GetCommandLineW` at `0x1400035f0`
- `KERNEL32!GetCommandLineW` at `0x1400035f0`
- `msvcrt!_wtol` at `0x1400036c5`
- `msvcrt!_wtol` at `0x1400036c5`
- `msvcrt!_wcsnicmp` at `0x1400036a4`
- `msvcrt!_wcsnicmp` at `0x1400036a4`
- `SHELL32!CommandLineToArgvW` at `0x14000362c`
- `SHELL32!CommandLineToArgvW` at `0x14000362c`

## pseudocode

```c
__int64 GetRestorePointIndexToWaitFor(void)
{
  unsigned int v0; // esi
  LPWSTR CommandLineW; // rax
  const WCHAR *v2; // rbx
  __int64 v3; // rdx
  LPWSTR *v4; // rdi
  __int64 v5; // r8
  int v6; // eax
  int i; // ebx
  const wchar_t *v8; // rcx
  int v9; // ecx
  _BYTE v11[120]; // [rsp+20h] [rbp-78h] BYREF
  int pNumArgs; // [rsp+A0h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v11, "GetRestorePointIndexToWaitFor", 788, 1);
  v0 = 0;
  pNumArgs = 0;
  CommandLineW = GetCommandLineW();
  v2 = CommandLineW;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids, CommandLineW);
  v4 = CommandLineToArgvW(v2, &pNumArgs);
  v6 = pNumArgs;
  if ( (!v4 || !pNumArgs)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
    v6 = pNumArgs;
  }
  for ( i = 0; i < v6; ++i )
  {
    v3 = -1;
    v8 = v4[i];
    do
      ++v3;
    while ( v8[v3] );
    if ( (unsigned int)v3 >= 0x16 )
    {
      if ( !_wcsnicmp(v8, L"/WaitForRestorePoint:", 0x15u) )
      {
        v9 = _wtol(v4[i] + 21);
        if ( (unsigned int)(v9 - 1) <= 0x7FFFFFFD )
          v0 = v9;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, v5, v0);
        }
        break;
      }
      v6 = pNumArgs;
    }
  }
  if ( v4 )
    LocalFree(v4);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v11, v3, v5);
  return v0;
}

```

## disassembly

```asm
0x140003584  push    rbx
0x140003586  push    rbp
0x140003587  push    rsi
0x140003588  push    rdi
0x140003589  push    r14
0x14000358b  push    r15
0x14000358d  sub     rsp, 68h
0x140003591  mov     rcx, cs:WPP_GLOBAL_Control
0x140003598  lea     r15, WPP_GLOBAL_Control
0x14000359f  lea     rbp, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x1400035a6  cmp     rcx, r15
0x1400035a9  jz      short loc_1400035C5
0x1400035ab  test    dword ptr [rcx+1Ch], 20000000h
0x1400035b2  jz      short loc_1400035C5
0x1400035b4  mov     rcx, [rcx+10h]
0x1400035b8  mov     edx, 2Dh ; '-'
0x1400035bd  mov     r8, rbp
0x1400035c0  call    WPP_SF_
0x1400035c5  mov     r9d, 1; unsigned __int16
0x1400035cb  lea     rdx, aGetrestorepoin; "GetRestorePointIndexToWaitFor"
0x1400035d2  mov     r8d, 314h; unsigned __int16
0x1400035d8  lea     rcx, [rsp+98h+var_78]; this
0x1400035dd  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1400035e2  xor     r14d, r14d
0x1400035e5  mov     esi, r14d
0x1400035e8  mov     [rsp+98h+pNumArgs], r14d
0x1400035f0  call    cs:__imp_GetCommandLineW
0x1400035f6  mov     rbx, rax
0x1400035f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140003600  cmp     rcx, r15
0x140003603  jz      short loc_140003621
0x140003605  test    dword ptr [rcx+1Ch], 8000000h
0x14000360c  jz      short loc_140003621
0x14000360e  mov     rcx, [rcx+10h]
0x140003612  lea     edx, [r14+2Eh]
0x140003616  mov     r9, rax
0x140003619  mov     r8, rbp
0x14000361c  call    WPP_SF_S
0x140003621  lea     rdx, [rsp+98h+pNumArgs]; pNumArgs
0x140003629  mov     rcx, rbx; lpCmdLine
0x14000362c  call    cs:__imp_CommandLineToArgvW
0x140003632  mov     rdi, rax
0x140003635  mov     eax, [rsp+98h+pNumArgs]
0x14000363c  test    rdi, rdi
0x14000363f  jz      short loc_140003645
0x140003641  test    eax, eax
0x140003643  jnz     short loc_140003672
0x140003645  mov     rcx, cs:WPP_GLOBAL_Control
0x14000364c  cmp     rcx, r15
0x14000364f  jz      short loc_140003672
0x140003651  test    dword ptr [rcx+1Ch], 8000000h
0x140003658  jz      short loc_140003672
0x14000365a  mov     rcx, [rcx+10h]
0x14000365e  mov     edx, 2Fh ; '/'
0x140003663  mov     r8, rbp
0x140003666  call    WPP_SF_
0x14000366b  mov     eax, [rsp+98h+pNumArgs]
0x140003672  mov     ebx, r14d
0x140003675  test    eax, eax
0x140003677  jle     loc_1400036FD
0x14000367d  movsxd  rbp, ebx
0x140003680  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140003684  mov     rcx, [rdi+rbp*8]; String1
0x140003688  inc     rdx
0x14000368b  cmp     [rcx+rdx*2], r14w
0x140003690  jnz     short loc_140003688
0x140003692  cmp     edx, 16h
0x140003695  jb      short loc_1400036B5
0x140003697  mov     r8d, 15h; MaxCount
0x14000369d  lea     rdx, aWaitforrestore_0; "/WaitForRestorePoint:"
0x1400036a4  call    cs:__imp__wcsnicmp
0x1400036aa  test    eax, eax
0x1400036ac  jz      short loc_1400036BD
0x1400036ae  mov     eax, [rsp+98h+pNumArgs]
0x1400036b5  inc     ebx
0x1400036b7  cmp     ebx, eax
0x1400036b9  jl      short loc_14000367D
0x1400036bb  jmp     short loc_1400036FD
0x1400036bd  mov     rcx, [rdi+rbp*8]
0x1400036c1  add     rcx, 2Ah ; '*'; String
0x1400036c5  call    cs:__imp__wtol
0x1400036cb  mov     ecx, eax
0x1400036cd  dec     eax
0x1400036cf  cmp     eax, 7FFFFFFDh
0x1400036d4  cmovbe  esi, ecx
0x1400036d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400036de  cmp     rcx, r15
0x1400036e1  jz      short loc_1400036FD
0x1400036e3  test    dword ptr [rcx+1Ch], 8000000h
0x1400036ea  jz      short loc_1400036FD
0x1400036ec  mov     rcx, [rcx+10h]
0x1400036f0  mov     edx, 30h ; '0'
0x1400036f5  mov     r9d, esi
0x1400036f8  call    WPP_SF_L
0x1400036fd  test    rdi, rdi
0x140003700  jz      short loc_14000370B
0x140003702  mov     rcx, rdi; hMem
0x140003705  call    cs:__imp_LocalFree
0x14000370b  lea     rcx, [rsp+98h+var_78]; this
0x140003710  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140003715  mov     eax, esi
0x140003717  add     rsp, 68h
0x14000371b  pop     r15
0x14000371d  pop     r14
0x14000371f  pop     rdi
0x140003720  pop     rsi
0x140003721  pop     rbp
0x140003722  pop     rbx
0x140003723  retn
```
