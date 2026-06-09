# ATL::CComObject<CSpObjectToken>::`scalar deleting destructor'(uint)

- ea: `0x18001a4c0`
- end: `0x18001a716`
- name: `??_G?$CComObject@VCSpObjectToken@@@ATL@@UEAAPEAXI@Z`
- size: `598`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18001a4c0`
- `0x180045938`
- `0x18007a2dc`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a660`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a660`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001a594`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001a5fe`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001a594`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001a5fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a586`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a5f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a586`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a5f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a694`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a6a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a694`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a6a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a645`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall ATL::CComObject<CSpObjectToken>::`scalar deleting destructor'(char *Block, char a2)
{
  LPVOID *v4; // rsi
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  LPVOID *v9; // r14
  const void *v10; // rdi
  HANDLE ProcessHeap; // rax
  SIZE_T v12; // rax
  SIZE_T v13; // rax
  unsigned __int64 v14; // rdx
  _WORD *v15; // rdi
  unsigned __int64 v16; // rcx
  __int64 i; // rcx
  const void *v18; // rdi
  HANDLE v19; // rax
  SIZE_T v20; // rax
  SIZE_T v21; // rax
  unsigned __int64 v22; // rdx
  _WORD *v23; // rdi
  unsigned __int64 v24; // rcx
  __int64 j; // rcx
  void *v27; // rcx
  void *v28; // rcx

  *(_QWORD *)Block = &ATL::CComObject<CSpObjectToken>::`vftable';
  *((_DWORD *)Block + 2) = -1073741823;
  v4 = (LPVOID *)(Block + 88);
  if ( *((_QWORD *)Block + 11) && !*((_QWORD *)Block + 14) )
  {
    v27 = (void *)*((_QWORD *)Block + 9);
    if ( v27 && !CloseHandle(v27) )
      SpHrFromLastWin32Error();
    v28 = (void *)*((_QWORD *)Block + 10);
    if ( v28 && !CloseHandle(v28) )
      SpHrFromLastWin32Error();
    *((_QWORD *)Block + 9) = 0;
    *((_QWORD *)Block + 10) = 0;
  }
  v5 = *((_QWORD *)Block + 15);
  if ( v5 )
  {
    *((_QWORD *)Block + 15) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v6 = *((_QWORD *)Block + 15);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)Block + 14);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = *((_QWORD *)Block + 13);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = (LPVOID *)(Block + 96);
  v10 = (const void *)*((_QWORD *)Block + 12);
  if ( v10 )
  {
    ProcessHeap = GetProcessHeap();
    v12 = HeapSize(ProcessHeap, 0, v10);
    if ( v12 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v13 = v12 >> 1;
      v14 = v13 - 1;
      if ( v13 - 1 >= 8 )
      {
        v15 = *v9;
        if ( *v9 > v9 || (v16 = 0, v14 = 8, v15 + 7 < (_WORD *)v9) )
        {
          for ( i = 8; i; --i )
            *v15++ = -8531;
          goto LABEL_19;
        }
        do
LABEL_43:
          *((_WORD *)*v9 + v16++) = -8531;
        while ( v16 < v14 );
        goto LABEL_19;
      }
      if ( v13 != 1 )
      {
        v16 = 0;
        goto LABEL_43;
      }
    }
LABEL_19:
    CoTaskMemFree(*v9);
    *v9 = 0;
  }
  v18 = *v4;
  if ( !*v4 )
    goto LABEL_29;
  v19 = GetProcessHeap();
  v20 = HeapSize(v19, 0, v18);
  if ( v20 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
  {
    v21 = v20 >> 1;
    v22 = v21 - 1;
    if ( v21 - 1 >= 8 )
    {
      v23 = *v4;
      if ( *v4 > v4 || (v24 = 0, v22 = 8, v23 + 7 < (_WORD *)v4) )
      {
        for ( j = 8; j; --j )
          *v23++ = -8531;
        goto LABEL_28;
      }
      do
LABEL_47:
        *((_WORD *)*v4 + v24++) = -8531;
      while ( v24 < v22 );
      goto LABEL_28;
    }
    if ( v21 != 1 )
    {
      v24 = 0;
      goto LABEL_47;
    }
  }
LABEL_28:
  CoTaskMemFree(*v4);
  *v4 = 0;
LABEL_29:
  if ( Block[56] )
  {
    Block[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18001a4c0  push    rbx
0x18001a4c2  push    rbp
0x18001a4c3  push    rsi
0x18001a4c4  push    rdi
0x18001a4c5  push    r12
0x18001a4c7  push    r13
0x18001a4c9  push    r14
0x18001a4cb  sub     rsp, 20h
0x18001a4cf  mov     ebp, edx
0x18001a4d1  mov     rbx, rcx
0x18001a4d4  lea     rax, ??_7?$CComObject@VCSpObjectToken@@@ATL@@6B@; const ATL::CComObject<CSpObjectToken>::`vftable'
0x18001a4db  mov     [rcx], rax
0x18001a4de  mov     dword ptr [rcx+8], 0C0000001h
0x18001a4e5  lea     rsi, [rcx+58h]
0x18001a4e9  cmp     qword ptr [rsi], 0
0x18001a4ed  jz      short loc_18001A4FA
0x18001a4ef  cmp     qword ptr [rcx+70h], 0
0x18001a4f4  jz      loc_18001A68B
0x18001a4fa  mov     rcx, [rbx+78h]
0x18001a4fe  test    rcx, rcx
0x18001a501  jz      short loc_18001A518
0x18001a503  mov     qword ptr [rbx+78h], 0
0x18001a50b  mov     rax, [rcx]
0x18001a50e  mov     rax, [rax+10h]
0x18001a512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a517  nop
0x18001a518  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001a51f  mov     rax, [rcx]
0x18001a522  mov     rax, [rax+10h]
0x18001a526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a52b  nop
0x18001a52c  mov     rcx, [rbx+78h]
0x18001a530  test    rcx, rcx
0x18001a533  jz      short loc_18001A542
0x18001a535  mov     rax, [rcx]
0x18001a538  mov     rax, [rax+10h]
0x18001a53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a541  nop
0x18001a542  mov     rcx, [rbx+70h]
0x18001a546  test    rcx, rcx
0x18001a549  jz      short loc_18001A558
0x18001a54b  mov     rax, [rcx]
0x18001a54e  mov     rax, [rax+10h]
0x18001a552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a557  nop
0x18001a558  mov     rcx, [rbx+68h]
0x18001a55c  test    rcx, rcx
0x18001a55f  jz      short loc_18001A56E
0x18001a561  mov     rax, [rcx]
0x18001a564  mov     rax, [rax+10h]
0x18001a568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a56d  nop
0x18001a56e  lea     r14, [rbx+60h]
0x18001a572  mov     rdi, [r14]
0x18001a575  mov     r12d, 8
0x18001a57b  mov     r13d, 0DEADh
0x18001a581  test    rdi, rdi
0x18001a584  jz      short loc_18001A5E8
0x18001a586  call    cs:__imp_GetProcessHeap
0x18001a58c  mov     r8, rdi; lpMem
0x18001a58f  xor     edx, edx; dwFlags
0x18001a591  mov     rcx, rax; hHeap
0x18001a594  call    cs:__imp_HeapSize
0x18001a59a  lea     rcx, [rax-3]
0x18001a59e  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x18001a5a2  ja      short loc_18001A5D8
0x18001a5a4  shr     rax, 1
0x18001a5a7  lea     rdx, [rax-1]
0x18001a5ab  cmp     rdx, r12
0x18001a5ae  jb      loc_18001A6C6
0x18001a5b4  mov     rdi, [r14]
0x18001a5b7  cmp     rdi, r14
0x18001a5ba  ja      short loc_18001A5CE
0x18001a5bc  xor     ecx, ecx
0x18001a5be  mov     edx, r12d
0x18001a5c1  lea     rax, [rdi+0Eh]
0x18001a5c5  cmp     rax, r14
0x18001a5c8  jnb     loc_18001A6D1
0x18001a5ce  movzx   eax, r13w
0x18001a5d2  mov     rcx, r12
0x18001a5d5  rep stosw
0x18001a5d8  mov     rcx, [r14]; pv
0x18001a5db  call    cs:__imp_CoTaskMemFree
0x18001a5e1  mov     qword ptr [r14], 0
0x18001a5e8  mov     rdi, [rsi]
0x18001a5eb  test    rdi, rdi
0x18001a5ee  jz      short loc_18001A652
0x18001a5f0  call    cs:__imp_GetProcessHeap
0x18001a5f6  mov     r8, rdi; lpMem
0x18001a5f9  xor     edx, edx; dwFlags
0x18001a5fb  mov     rcx, rax; hHeap
0x18001a5fe  call    cs:__imp_HeapSize
0x18001a604  lea     rcx, [rax-3]
0x18001a608  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x18001a60c  ja      short loc_18001A642
0x18001a60e  shr     rax, 1
0x18001a611  lea     rdx, [rax-1]
0x18001a615  cmp     rdx, r12
0x18001a618  jb      loc_18001A6E7
0x18001a61e  mov     rdi, [rsi]
0x18001a621  cmp     rdi, rsi
0x18001a624  ja      short loc_18001A638
0x18001a626  xor     ecx, ecx
0x18001a628  mov     rdx, r12
0x18001a62b  lea     rax, [rdi+0Eh]
0x18001a62f  cmp     rax, rsi
0x18001a632  jnb     loc_18001A6F2
0x18001a638  movzx   eax, r13w
0x18001a63c  mov     rcx, r12
0x18001a63f  rep stosw
0x18001a642  mov     rcx, [rsi]; pv
0x18001a645  call    cs:__imp_CoTaskMemFree
0x18001a64b  mov     qword ptr [rsi], 0
0x18001a652  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001a656  cmp     byte ptr [rcx+28h], 0
0x18001a65a  jz      short loc_18001A666
0x18001a65c  mov     byte ptr [rcx+28h], 0
0x18001a660  call    cs:__imp_DeleteCriticalSection
0x18001a666  test    bpl, 1
0x18001a66a  jz      short loc_18001A679
0x18001a66c  mov     edx, 80h
0x18001a671  mov     rcx, rbx; Block
0x18001a674  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a679  mov     rax, rbx
0x18001a67c  add     rsp, 20h
0x18001a680  pop     r14
0x18001a682  pop     r13
0x18001a684  pop     r12
0x18001a686  pop     rdi
0x18001a687  pop     rsi
0x18001a688  pop     rbp
0x18001a689  pop     rbx
0x18001a68a  retn
0x18001a68b  mov     rcx, [rcx+48h]; hObject
0x18001a68f  test    rcx, rcx
0x18001a692  jz      short loc_18001A69E
0x18001a694  call    cs:__imp_CloseHandle
0x18001a69a  test    eax, eax
0x18001a69c  jz      short loc_18001A708
0x18001a69e  mov     rcx, [rbx+50h]; hObject
0x18001a6a2  test    rcx, rcx
0x18001a6a5  jz      short loc_18001A6B1
0x18001a6a7  call    cs:__imp_CloseHandle
0x18001a6ad  test    eax, eax
0x18001a6af  jz      short loc_18001A70F
0x18001a6b1  mov     qword ptr [rbx+48h], 0
0x18001a6b9  mov     qword ptr [rbx+50h], 0
0x18001a6c1  jmp     loc_18001A4FA
0x18001a6c6  test    rdx, rdx
0x18001a6c9  jz      loc_18001A5D8
0x18001a6cf  xor     ecx, ecx
0x18001a6d1  mov     rax, [r14]
0x18001a6d4  mov     [rax+rcx*2], r13w
0x18001a6d9  inc     rcx
0x18001a6dc  cmp     rcx, rdx
0x18001a6df  jnb     loc_18001A5D8
0x18001a6e5  jmp     short loc_18001A6D1
0x18001a6e7  test    rdx, rdx
0x18001a6ea  jz      loc_18001A642
0x18001a6f0  xor     ecx, ecx
0x18001a6f2  mov     rax, [rsi]
0x18001a6f5  mov     [rax+rcx*2], r13w
0x18001a6fa  inc     rcx
0x18001a6fd  cmp     rcx, rdx
0x18001a700  jnb     loc_18001A642
0x18001a706  jmp     short loc_18001A6F2
0x18001a708  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x18001a70d  jmp     short loc_18001A69E
0x18001a70f  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x18001a714  jmp     short loc_18001A6B1
```
