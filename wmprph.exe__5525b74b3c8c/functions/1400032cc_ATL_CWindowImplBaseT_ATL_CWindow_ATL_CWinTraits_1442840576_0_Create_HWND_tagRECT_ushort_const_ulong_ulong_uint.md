# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,tagRECT &,ushort const *,ulong,ulong,uint,ushort,void *)

- ea: `0x1400032cc`
- end: `0x140003405`
- name: `?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@AEAUtagRECT@@PEBGKKIGPEAX@Z`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400053a0`
- `0x140005450`

## callees

- `0x1400032cc`
- `0x14000902c`
- `0x14000d780`
- `0x14000d89c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000334a`
- `KERNEL32!GetCurrentThreadId` at `0x14000334a`
- `KERNEL32!LeaveCriticalSection` at `0x140003379`
- `KERNEL32!LeaveCriticalSection` at `0x140003379`
- `KERNEL32!EnterCriticalSection` at `0x14000335a`
- `KERNEL32!EnterCriticalSection` at `0x14000335a`
- `KERNEL32!SetLastError` at `0x140003300`
- `KERNEL32!SetLastError` at `0x140003300`
- `USER32!CreateWindowExW` at `0x1400033f4`
- `USER32!CreateWindowExW` at `0x1400033f4`

## pseudocode

```c
HWND __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(
        __int64 a1,
        __int64 a2,
        int *a3,
        const WCHAR *a4,
        DWORD dwStyle,
        DWORD dwExStyle,
        __int64 a7,
        unsigned __int16 a8)
{
  AtlThunkData_t *Data; // rax
  unsigned int v13; // edx
  unsigned int v14; // ecx
  unsigned __int32 v15; // edi

  Data = *(AtlThunkData_t **)(a1 + 40);
  if ( !Data )
  {
    Data = AtlThunk_AllocateData();
    *(_QWORD *)(a1 + 40) = Data;
    if ( !Data )
    {
      SetLastError(0xEu);
      return 0;
    }
  }
  AtlThunk_InitData(Data, 0, 0);
  if ( !a8 )
    return 0;
  if ( a1 == -16 || !a1 )
  {
    ATL::_AtlRaiseException(v14, v13);
    JUMPOUT(0x140003404LL);
  }
  v15 = 0;
  *(_QWORD *)(a1 + 16) = a1;
  *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
  EnterCriticalSection(&CriticalSection);
  *(_QWORD *)(a1 + 32) = qword_140015468;
  qword_140015468 = a1 + 16;
  LeaveCriticalSection(&CriticalSection);
  if ( (dwStyle & 0x40000000) != 0 )
    v15 = _InterlockedIncrement(&dword_1400154A0);
  return CreateWindowExW(
           dwExStyle,
           (LPCWSTR)a8,
           a4,
           dwStyle,
           *a3,
           a3[1],
           a3[2] - *a3,
           a3[3] - a3[1],
           0,
           (HMENU)v15,
           hInstance,
           0);
}

```

## disassembly

```asm
0x1400032cc  push    rbx
0x1400032ce  push    rsi
0x1400032cf  push    rdi
0x1400032d0  push    r12
0x1400032d2  push    r14
0x1400032d4  push    r15
0x1400032d6  sub     rsp, 68h
0x1400032da  mov     rax, [rcx+28h]
0x1400032de  xor     r12d, r12d
0x1400032e1  mov     r15, r9
0x1400032e4  mov     r14, r8
0x1400032e7  mov     rbx, rcx
0x1400032ea  test    rax, rax
0x1400032ed  jnz     short loc_140003316
0x1400032ef  call    AtlThunk_AllocateData
0x1400032f4  mov     [rbx+28h], rax
0x1400032f8  test    rax, rax
0x1400032fb  jnz     short loc_140003316
0x1400032fd  lea     ecx, [rax+0Eh]; dwErrCode
0x140003300  call    cs:__imp_SetLastError
0x140003306  xor     eax, eax
0x140003308  add     rsp, 68h
0x14000330c  pop     r15
0x14000330e  pop     r14
0x140003310  pop     r12
0x140003312  pop     rdi
0x140003313  pop     rsi
0x140003314  pop     rbx
0x140003315  retn
0x140003316  xor     r8d, r8d; FirstParameter
0x140003319  xor     edx, edx; Proc
0x14000331b  mov     rcx, rax; Thunk
0x14000331e  call    AtlThunk_InitData
0x140003323  cmp     [rsp+98h+arg_38], r12w
0x14000332c  jz      short loc_140003306
0x14000332e  lea     rsi, [rbx+10h]
0x140003332  test    rsi, rsi
0x140003335  jz      loc_1400033FF
0x14000333b  test    rbx, rbx
0x14000333e  jz      loc_1400033FF
0x140003344  mov     edi, r12d
0x140003347  mov     [rsi], rbx
0x14000334a  call    cs:__imp_GetCurrentThreadId
0x140003350  lea     rcx, CriticalSection; lpCriticalSection
0x140003357  mov     [rsi+8], eax
0x14000335a  call    cs:__imp_EnterCriticalSection
0x140003360  mov     rax, cs:qword_140015468
0x140003367  lea     rcx, CriticalSection; lpCriticalSection
0x14000336e  mov     [rsi+10h], rax
0x140003372  mov     cs:qword_140015468, rsi
0x140003379  call    cs:__imp_LeaveCriticalSection
0x14000337f  mov     r9d, [rsp+98h+dwStyle]; dwStyle
0x140003387  bt      r9d, 1Eh
0x14000338c  jnb     short loc_14000339D
0x14000338e  mov     edi, 1
0x140003393  lock xadd cs:dword_1400154A0, edi
0x14000339b  inc     edi
0x14000339d  mov     r11d, [r14+4]
0x1400033a1  mov     r8d, [r14+8]
0x1400033a5  mov     ebx, [r14]
0x1400033a8  sub     r8d, ebx
0x1400033ab  mov     rax, cs:hInstance
0x1400033b2  mov     r10d, [r14+0Ch]
0x1400033b6  movzx   edx, [rsp+98h+arg_38]; lpClassName
0x1400033be  sub     r10d, r11d
0x1400033c1  mov     [rsp+98h+lpParam], r12; lpParam
0x1400033c6  mov     [rsp+98h+hInstance], rax; hInstance
0x1400033cb  mov     ecx, edi
0x1400033cd  mov     [rsp+98h+hMenu], rcx; hMenu
0x1400033d2  mov     ecx, [rsp+98h+dwExStyle]; dwExStyle
0x1400033d9  mov     [rsp+98h+hWndParent], r12; hWndParent
0x1400033de  mov     [rsp+98h+nHeight], r10d; nHeight
0x1400033e3  mov     [rsp+98h+nWidth], r8d; nWidth
0x1400033e8  mov     r8, r15; lpWindowName
0x1400033eb  mov     [rsp+98h+Y], r11d; Y
0x1400033f0  mov     [rsp+98h+X], ebx; X
0x1400033f4  call    cs:__imp_CreateWindowExW
0x1400033fa  jmp     loc_140003308
0x1400033ff  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
