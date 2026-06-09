# InternalDdeInitialize(ulong *,HDDEDATA__ * (*)(uint,uint,HCONV__ *,HSZ__ *,HSZ__ *,HDDEDATA__ *,unsigned __int64,unsigned __int64),ulong,int)

- ea: `0x180046aa8`
- end: `0x180046cfe`
- name: `?InternalDdeInitialize@@YAIPEAKP6APEAUHDDEDATA__@@IIPEAUHCONV__@@PEAUHSZ__@@2PEAU1@_K4@ZKH@Z`
- size: `598`
- prototype: `unsigned int __fastcall(unsigned int *, HDDEDATA (*)(unsigned int, unsigned int, HCONV, HSZ, HSZ, HDDEDATA, unsigned __int64, unsigned __int64), unsigned int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180066380`
- `0x1800781b0`

## callees

- `0x180016310`
- `0x18002ddb0`
- `0x180046aa8`
- `0x180046d04`
- `0x18004812c`

## import_xrefs

- `win32u!NtUserCsDdeUninitialize` at `0x180046cde`
- `win32u!NtUserCsDdeUninitialize` at `0x180046cde`
- `win32u!NtUserDdeInitialize` at `0x180046bdd`
- `win32u!NtUserDdeInitialize` at `0x180046bdd`
- `win32u!NtUserUpdateInstance` at `0x180046c99`
- `win32u!NtUserUpdateInstance` at `0x180046c99`
- `win32u!NtUserDestroyWindow` at `0x180046cf6`
- `win32u!NtUserDestroyWindow` at `0x180046cf6`
- `ntdll!RtlEnterCriticalSection` at `0x180046aec`
- `ntdll!RtlEnterCriticalSection` at `0x180046be8`
- `ntdll!RtlEnterCriticalSection` at `0x180046ce7`
- `ntdll!RtlEnterCriticalSection` at `0x180046aec`
- `ntdll!RtlEnterCriticalSection` at `0x180046be8`
- `ntdll!RtlEnterCriticalSection` at `0x180046ce7`
- `ntdll!RtlLeaveCriticalSection` at `0x180046bbf`
- `ntdll!RtlLeaveCriticalSection` at `0x180046c4e`
- `ntdll!RtlLeaveCriticalSection` at `0x180046c88`
- `ntdll!RtlLeaveCriticalSection` at `0x180046cd5`
- `ntdll!RtlLeaveCriticalSection` at `0x180046bbf`
- `ntdll!RtlLeaveCriticalSection` at `0x180046c4e`
- `ntdll!RtlLeaveCriticalSection` at `0x180046c88`
- `ntdll!RtlLeaveCriticalSection` at `0x180046cd5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046b04`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046b1e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046b04`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046b1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046cac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046cb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046cac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046cb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046bb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046bb3`

## pseudocode

```c
__int64 __fastcall InternalDdeInitialize(
        unsigned int *a1,
        HDDEDATA (*a2)(unsigned int, unsigned int, HCONV, HSZ, HSZ, HDDEDATA, unsigned __int64, unsigned __int64),
        int a3,
        int a4)
{
  int v4; // r10d
  int v8; // edi
  char *v9; // rbx
  HLOCAL v10; // rax
  __int64 v11; // rax
  HWND WindowInternal; // rax
  void **v13; // rsi
  unsigned int v14; // edi
  void *v15; // rax
  unsigned __int64 v16; // rdx
  struct tagCL_INSTANCE_INFO *v18; // rax
  struct tagCL_INSTANCE_INFO *v19; // rbx

  v4 = a3 | 0x27F000;
  if ( (a3 & 1) == 0 )
    v4 = a3;
  v8 = v4 | 0x2000;
  if ( (v4 & 0x10) == 0 )
    v8 = v4;
  RtlEnterCriticalSection(&gcsDDEML);
  if ( !*a1 )
  {
    v9 = (char *)LocalAlloc(0x40u, 0x78u);
    if ( v9 )
    {
      v10 = LocalAlloc(0x40u, 2u);
      *((_QWORD *)v9 + 10) = v10;
      if ( v10 )
      {
        v11 = gpsi;
        *((_WORD *)v9 + 44) = 1;
        WindowInternal = (HWND)CreateWindowInternal(0, *(unsigned __int16 *)(v11 + 886), &pszFormat);
        *((_QWORD *)v9 + 4) = WindowInternal;
        if ( WindowInternal )
        {
          SetWindowLongPtrW(WindowInternal, 0, (LONG_PTR)v9);
          *((_QWORD *)v9 + 8) = a2;
          *((_DWORD *)v9 + 14) = v8 | 0x20;
          *((_DWORD *)v9 + 19) = GetCurrentThreadId();
          RtlLeaveCriticalSection(&gcsDDEML);
          v13 = (void **)(v9 + 8);
          v14 = NtUserDdeInitialize(v9 + 8, v9 + 40, v9 + 24, *((unsigned int *)v9 + 14), v9);
          RtlEnterCriticalSection(&gcsDDEML);
          if ( !v14 )
          {
            v15 = AddInstance(*v13);
            *((_QWORD *)v9 + 2) = v15;
            *a1 = (unsigned int)v15;
            v16 = *((_QWORD *)v9 + 2);
            if ( v16 )
            {
              *((_QWORD *)aHandleEntry + 2 * ((v16 >> 10) & 0x3FFF) + 1) = v9;
              *(_QWORD *)v9 = pciiList;
              pciiList = (struct tagCL_INSTANCE_INFO *)v9;
              if ( a4 )
                *((_WORD *)v9 + 54) |= 0x8000u;
              v14 = 0;
              goto LABEL_14;
            }
            RtlLeaveCriticalSection(&gcsDDEML);
            NtUserCsDdeUninitialize(*v13);
            RtlEnterCriticalSection(&gcsDDEML);
            v14 = 16392;
          }
          NtUserDestroyWindow(*((_QWORD *)v9 + 4));
        }
        else
        {
          v14 = 16399;
        }
        LocalFree(*((HLOCAL *)v9 + 10));
      }
      else
      {
        v14 = 16392;
      }
      LocalFree(v9);
    }
    else
    {
      v14 = 16392;
    }
LABEL_14:
    RtlLeaveCriticalSection(&gcsDDEML);
    return v14;
  }
  v18 = ValidateInstance((void *)(int)*a1);
  v19 = v18;
  if ( !v18 )
  {
    v14 = 16390;
    goto LABEL_14;
  }
  *((_DWORD *)v18 + 14) = v8 ^ (*((_DWORD *)v18 + 14) ^ v8) & 0xC00FFF;
  RtlLeaveCriticalSection(&gcsDDEML);
  NtUserUpdateInstance(*((_QWORD *)v19 + 1), (char *)v19 + 24);
  return 0;
}

```

## disassembly

```asm
0x180046aa8  push    rbx
0x180046aaa  push    rbp
0x180046aab  push    rsi
0x180046aac  push    rdi
0x180046aad  push    r12
0x180046aaf  push    r14
0x180046ab1  sub     rsp, 88h
0x180046ab8  mov     r10d, r8d
0x180046abb  lea     r12, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION gcsDDEML
0x180046ac2  or      r10d, 27F000h
0x180046ac9  mov     r14, rcx
0x180046acc  test    r8b, 1
0x180046ad0  mov     rcx, r12; CriticalSection
0x180046ad3  mov     ebp, r9d
0x180046ad6  mov     rsi, rdx
0x180046ad9  cmovz   r10d, r8d
0x180046add  mov     edi, r10d
0x180046ae0  bts     edi, 0Dh
0x180046ae4  test    r10b, 10h
0x180046ae8  cmovz   edi, r10d
0x180046aec  call    cs:__imp_RtlEnterCriticalSection
0x180046af2  cmp     dword ptr [r14], 0
0x180046af6  jnz     loc_180046C66
0x180046afc  mov     edx, 78h ; 'x'; uBytes
0x180046b01  lea     ecx, [rdx-38h]; uFlags
0x180046b04  call    cs:__imp_LocalAlloc
0x180046b0a  mov     rbx, rax
0x180046b0d  test    rax, rax
0x180046b10  jz      loc_180046CC4
0x180046b16  mov     edx, 2; uBytes
0x180046b1b  lea     ecx, [rdx+3Eh]; uFlags
0x180046b1e  call    cs:__imp_LocalAlloc
0x180046b24  mov     [rbx+50h], rax
0x180046b28  test    rax, rax
0x180046b2b  jz      loc_180046CCB
0x180046b31  mov     rax, cs:gpsi
0x180046b38  lea     r8, pszFormat
0x180046b3f  xor     ecx, ecx
0x180046b41  mov     word ptr [rbx+58h], 1
0x180046b47  mov     [rsp+0B8h+var_40], cx
0x180046b4c  mov     r9d, 80000000h
0x180046b52  mov     [rsp+0B8h+var_48], ecx
0x180046b56  movzx   edx, word ptr [rax+376h]
0x180046b5d  mov     [rsp+0B8h+var_50], r9d
0x180046b62  mov     [rsp+0B8h+var_58], ecx
0x180046b66  mov     [rsp+0B8h+var_60], rcx
0x180046b6b  mov     [rsp+0B8h+var_68], rcx
0x180046b70  mov     [rsp+0B8h+var_70], rcx
0x180046b75  mov     [rsp+0B8h+var_78], rcx
0x180046b7a  mov     [rsp+0B8h+var_80], ecx
0x180046b7e  mov     [rsp+0B8h+var_88], ecx
0x180046b82  mov     [rsp+0B8h+var_90], ecx
0x180046b86  mov     dword ptr [rsp+0B8h+var_98], ecx
0x180046b8a  call    CreateWindowInternal
0x180046b8f  mov     [rbx+20h], rax
0x180046b93  test    rax, rax
0x180046b96  jz      loc_180046CA3
0x180046b9c  mov     r8, rbx; dwNewLong
0x180046b9f  xor     edx, edx; nIndex
0x180046ba1  mov     rcx, rax; hWnd
0x180046ba4  call    SetWindowLongPtrW
0x180046ba9  or      edi, 20h
0x180046bac  mov     [rbx+40h], rsi
0x180046bb0  mov     [rbx+38h], edi
0x180046bb3  call    cs:__imp_GetCurrentThreadId
0x180046bb9  mov     rcx, r12; CriticalSection
0x180046bbc  mov     [rbx+4Ch], eax
0x180046bbf  call    cs:__imp_RtlLeaveCriticalSection
0x180046bc5  mov     r9d, [rbx+38h]
0x180046bc9  lea     rsi, [rbx+8]
0x180046bcd  mov     rcx, rsi
0x180046bd0  mov     [rsp+0B8h+var_98], rbx
0x180046bd5  lea     r8, [rbx+18h]
0x180046bd9  lea     rdx, [rbx+28h]
0x180046bdd  call    cs:__imp_NtUserDdeInitialize
0x180046be3  mov     rcx, r12; CriticalSection
0x180046be6  mov     edi, eax
0x180046be8  call    cs:__imp_RtlEnterCriticalSection
0x180046bee  test    edi, edi
0x180046bf0  jnz     loc_180046CF2
0x180046bf6  mov     rcx, [rsi]; void *
0x180046bf9  call    ?AddInstance@@YAPEAXPEAX@Z; AddInstance(void *)
0x180046bfe  mov     [rbx+10h], rax
0x180046c02  mov     [r14], eax
0x180046c05  mov     rdx, [rbx+10h]
0x180046c09  test    rdx, rdx
0x180046c0c  jz      loc_180046CD2
0x180046c12  mov     rax, cs:?aHandleEntry@@3PEAUtagCHANDLEENTRY@@EA; tagCHANDLEENTRY * aHandleEntry
0x180046c19  shr     rdx, 0Ah
0x180046c1d  and     edx, 3FFFh
0x180046c23  add     rdx, rdx
0x180046c26  mov     [rax+rdx*8+8], rbx
0x180046c2b  mov     rax, cs:?pciiList@@3PEAUtagCL_INSTANCE_INFO@@EA; tagCL_INSTANCE_INFO * pciiList
0x180046c32  mov     [rbx], rax
0x180046c35  mov     cs:?pciiList@@3PEAUtagCL_INSTANCE_INFO@@EA, rbx; tagCL_INSTANCE_INFO * pciiList
0x180046c3c  test    ebp, ebp
0x180046c3e  jz      short loc_180046C49
0x180046c40  mov     eax, 8000h
0x180046c45  or      [rbx+6Ch], ax
0x180046c49  xor     edi, edi
0x180046c4b  mov     rcx, r12; CriticalSection
0x180046c4e  call    cs:__imp_RtlLeaveCriticalSection
0x180046c54  mov     eax, edi
0x180046c56  add     rsp, 88h
0x180046c5d  pop     r14
0x180046c5f  pop     r12
0x180046c61  pop     rdi
0x180046c62  pop     rsi
0x180046c63  pop     rbp
0x180046c64  pop     rbx
0x180046c65  retn
0x180046c66  movsxd  rcx, dword ptr [r14]; void *
0x180046c69  call    ?ValidateInstance@@YAPEAUtagCL_INSTANCE_INFO@@PEAX@Z; ValidateInstance(void *)
0x180046c6e  mov     rbx, rax
0x180046c71  test    rax, rax
0x180046c74  jz      short loc_180046CBD
0x180046c76  mov     eax, edi
0x180046c78  mov     rcx, r12; CriticalSection
0x180046c7b  xor     eax, [rbx+38h]
0x180046c7e  and     eax, 0C00FFFh
0x180046c83  xor     eax, edi
0x180046c85  mov     [rbx+38h], eax
0x180046c88  call    cs:__imp_RtlLeaveCriticalSection
0x180046c8e  mov     rcx, [rbx+8]
0x180046c92  lea     rdx, [rbx+18h]
0x180046c96  mov     r8d, edi
0x180046c99  call    cs:__imp_NtUserUpdateInstance
0x180046c9f  xor     eax, eax
0x180046ca1  jmp     short loc_180046C56
0x180046ca3  mov     edi, 400Fh
0x180046ca8  mov     rcx, [rbx+50h]; hMem
0x180046cac  call    cs:__imp_LocalFree
0x180046cb2  mov     rcx, rbx; hMem
0x180046cb5  call    cs:__imp_LocalFree
0x180046cbb  jmp     short loc_180046C4B
0x180046cbd  mov     edi, 4006h
0x180046cc2  jmp     short loc_180046C4B
0x180046cc4  mov     edi, 4008h
0x180046cc9  jmp     short loc_180046C4B
0x180046ccb  mov     edi, 4008h
0x180046cd0  jmp     short loc_180046CB2
0x180046cd2  mov     rcx, r12; CriticalSection
0x180046cd5  call    cs:__imp_RtlLeaveCriticalSection
0x180046cdb  mov     rcx, [rsi]
0x180046cde  call    cs:__imp_NtUserCsDdeUninitialize
0x180046ce4  mov     rcx, r12; CriticalSection
0x180046ce7  call    cs:__imp_RtlEnterCriticalSection
0x180046ced  mov     edi, 4008h
0x180046cf2  mov     rcx, [rbx+20h]
0x180046cf6  call    cs:__imp_NtUserDestroyWindow
0x180046cfc  jmp     short loc_180046CA8
```
