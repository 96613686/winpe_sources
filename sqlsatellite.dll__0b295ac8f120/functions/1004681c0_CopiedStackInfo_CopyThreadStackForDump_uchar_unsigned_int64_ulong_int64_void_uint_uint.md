# CopiedStackInfo::CopyThreadStackForDump(uchar *,unsigned __int64,ulong,__int64 (**)(void),uint,uint &)

- ea: `0x1004681c0`
- end: `0x1004685a6`
- name: `?CopyThreadStackForDump@CopiedStackInfo@@QEAA_NPEAE_KKPEAP6A_JXZIAEAI@Z`
- size: `998`
- prototype: `bool(CopiedStackInfo *__hidden this, unsigned __int8 *, unsigned __int64, unsigned int, __int64 (**)(void), unsigned int, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x100465450`
- `0x100465cb0`
- `0x1004661f0`
- `0x100466700`

## callees

- `0x10045d400`
- `0x1004681c0`
- `0x1004815a0`

## import_xrefs

- `KERNEL32!OpenThread` at `0x100468262`
- `KERNEL32!OpenThread` at `0x100468262`
- `KERNEL32!SuspendThread` at `0x1004682ba`
- `KERNEL32!SuspendThread` at `0x1004682ba`
- `KERNEL32!ResumeThread` at `0x10046848d`
- `KERNEL32!ResumeThread` at `0x10046848d`
- `KERNEL32!GetThreadContext` at `0x10046831f`
- `KERNEL32!GetThreadContext` at `0x10046831f`
- `KERNEL32!QueryPerformanceCounter` at `0x100468234`
- `KERNEL32!QueryPerformanceCounter` at `0x100468294`
- `KERNEL32!QueryPerformanceCounter` at `0x1004682f0`
- `KERNEL32!QueryPerformanceCounter` at `0x100468361`
- `KERNEL32!QueryPerformanceCounter` at `0x100468403`
- `KERNEL32!QueryPerformanceCounter` at `0x10046854e`
- `KERNEL32!QueryPerformanceCounter` at `0x100468234`
- `KERNEL32!QueryPerformanceCounter` at `0x100468294`
- `KERNEL32!QueryPerformanceCounter` at `0x1004682f0`
- `KERNEL32!QueryPerformanceCounter` at `0x100468361`
- `KERNEL32!QueryPerformanceCounter` at `0x100468403`
- `KERNEL32!QueryPerformanceCounter` at `0x10046854e`
- `KERNEL32!VirtualQuery` at `0x10046839a`
- `KERNEL32!VirtualQuery` at `0x10046839a`
- `KERNEL32!GetCurrentThreadId` at `0x1004681f0`
- `KERNEL32!GetCurrentThreadId` at `0x1004681f0`
- `KERNEL32!CloseHandle` at `0x10046857e`
- `KERNEL32!CloseHandle` at `0x10046857e`
- `KERNEL32!GetLastError` at `0x1004684a1`
- `KERNEL32!GetLastError` at `0x1004684a1`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100468221`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100468283`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004682d7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100468348`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004683ea`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10046853a`

## pseudocode

```c
_BOOL8 __fastcall CopiedStackInfo::CopyThreadStackForDump(
        CopiedStackInfo *this,
        unsigned __int8 *a2,
        SIZE_T a3,
        DWORD a4,
        __int64 (**a5)(void),
        unsigned int a6,
        unsigned int *PerformanceCount)
{
  char v11; // al
  void *v12; // rbx
  unsigned int *v13; // rax
  HANDLE v14; // r14
  LARGE_INTEGER v15; // rcx
  LARGE_INTEGER v16; // rax
  LARGE_INTEGER v17; // rax
  SIZE_T v18; // rsi
  LARGE_INTEGER v19; // rax
  __int64 v20; // r8
  __int64 *v21; // rdx
  __int64 v22; // rcx
  __int64 *v23; // rcx
  __int64 v24; // rdx
  LARGE_INTEGER v25; // rax
  bool v27; // [rsp+20h] [rbp-D8h]
  SIZE_T nSize; // [rsp+30h] [rbp-C8h]
  _QWORD *v29; // [rsp+38h] [rbp-C0h]
  LARGE_INTEGER v30; // [rsp+48h] [rbp-B0h] BYREF
  LARGE_INTEGER v31; // [rsp+50h] [rbp-A8h]
  LARGE_INTEGER v32; // [rsp+58h] [rbp-A0h] BYREF
  LARGE_INTEGER v33; // [rsp+60h] [rbp-98h]
  LARGE_INTEGER v34; // [rsp+68h] [rbp-90h] BYREF
  LARGE_INTEGER v35; // [rsp+70h] [rbp-88h]
  LARGE_INTEGER v36; // [rsp+78h] [rbp-80h] BYREF
  LARGE_INTEGER v37; // [rsp+80h] [rbp-78h]
  HANDLE v38; // [rsp+88h] [rbp-70h]
  LARGE_INTEGER v39; // [rsp+90h] [rbp-68h] BYREF
  struct _MEMORY_BASIC_INFORMATION Buffer; // [rsp+98h] [rbp-60h] BYREF

  v27 = 0;
  if ( a4 != GetCurrentThreadId() )
  {
    v11 = *(_BYTE *)this;
    *(_BYTE *)this = 1;
    if ( !v11 )
    {
      v12 = 0;
      v29 = 0;
      *((_DWORD *)this + 1) = 1;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter((LARGE_INTEGER *)&PerformanceCount);
        v13 = PerformanceCount;
      }
      else
      {
        v13 = (unsigned int *)MEMORY[0x7FFE0008];
        v12 = 0;
      }
      *((_QWORD *)this + 1) = v13;
      v14 = OpenThread(0x4Au, 0, a4);
      v38 = v14;
      if ( !v14
        || ((*((_DWORD *)this + 1) = 2, !Base_PublicGlobals::sm_invariantTscAvailable)
          ? (v15.QuadPart = MEMORY[0x7FFE0008], v12 = 0)
          : (void *)(QueryPerformanceCounter(&v30), v15 = v30),
            v31 = v15,
            *((LARGE_INTEGER *)this + 1) = v15,
            SuspendThread(v14) == -1) )
      {
        v18 = nSize;
      }
      else
      {
        *((_DWORD *)this + 24) = 1048587;
        *((_DWORD *)this + 1) = 3;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v32);
          v16 = v32;
          v33 = v32;
        }
        else
        {
          v16.QuadPart = MEMORY[0x7FFE0008];
          v33.QuadPart = MEMORY[0x7FFE0008];
          v12 = 0;
        }
        *((LARGE_INTEGER *)this + 1) = v16;
        if ( !GetThreadContext(v14, (LPCONTEXT)((char *)this + 48)) )
          goto LABEL_27;
        v29 = (_QWORD *)((char *)this + 200);
        v12 = (void *)*((_QWORD *)this + 25);
        *((_DWORD *)this + 1) = 4;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v34);
          v17 = v34;
          v35 = v34;
        }
        else
        {
          v17.QuadPart = MEMORY[0x7FFE0008];
          v35.QuadPart = MEMORY[0x7FFE0008];
        }
        *((LARGE_INTEGER *)this + 1) = v17;
        if ( VirtualQuery(v12, &Buffer, 0x30u) && Buffer.AllocationProtect == 4 )
        {
          v18 = Buffer.RegionSize + (char *)Buffer.BaseAddress - (char *)v12;
          if ( v18 > a3 )
            v18 = a3;
          *((_QWORD *)this + 3) = a2;
          *((_QWORD *)this + 4) = v18;
          *((_DWORD *)this + 1) = 5;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v36);
            v19 = v36;
            v37 = v36;
          }
          else
          {
            v19.QuadPart = MEMORY[0x7FFE0008];
            v37.QuadPart = MEMORY[0x7FFE0008];
          }
          *((LARGE_INTEGER *)this + 1) = v19;
          if ( (v18 & 7) == 0 )
          {
            _mm_lfence();
            v27 = (unsigned int)DmpCopyMemorySafely(*((void **)this + 3), v12, v18) == 0;
          }
        }
        else
        {
LABEL_27:
          v18 = nSize;
        }
        ResumeThread(v14);
      }
      if ( v27 )
      {
        *((_QWORD *)this + 314) = v12;
        v20 = *((_QWORD *)this + 3) - (_QWORD)v12;
        *v29 += v20;
        v21 = (__int64 *)*((_QWORD *)this + 3);
        if ( v21 < (__int64 *)((char *)v21 + v18) )
        {
          do
          {
            v22 = *v21;
            if ( *v21 >= (unsigned __int64)v12 && v22 - (__int64)v12 <= v18 )
              *v21 = v22 + v20;
            ++v21;
          }
          while ( (unsigned __int64)v21 < v18 + *((_QWORD *)this + 3) );
        }
        v23 = (__int64 *)((char *)this + 48);
        if ( (char *)this + 48 < (char *)this + 1280 )
        {
          do
          {
            v24 = *v23;
            if ( *v23 >= (unsigned __int64)v12 && v24 - (__int64)v12 <= v18 )
              *v23 = v24 + v20;
            ++v23;
          }
          while ( v23 < (__int64 *)this + 160 );
        }
        *((_DWORD *)this + 1) = 6;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v39);
          v25 = v39;
        }
        else
        {
          v25.QuadPart = MEMORY[0x7FFE0008];
        }
        *((LARGE_INTEGER *)this + 1) = v25;
        log_unlocalized(L"Failed to collect non yield stack frames.\n");
      }
      else
      {
        *((_DWORD *)this + 4) = GetLastError();
        *(_BYTE *)this = 0;
      }
      if ( v14 )
        CloseHandle(v14);
    }
  }
  return v27;
}

```

## disassembly

```asm
0x1004681c0  mov     [rsp+arg_8], rbx
0x1004681c5  mov     [rsp+arg_10], rsi
0x1004681ca  mov     [rsp+arg_0], rcx
0x1004681cf  push    rdi
0x1004681d0  push    r12
0x1004681d2  push    r13
0x1004681d4  push    r14
0x1004681d6  push    r15
0x1004681d8  sub     rsp, 0D0h
0x1004681df  mov     esi, r9d
0x1004681e2  mov     r15, r8
0x1004681e5  mov     r12, rdx
0x1004681e8  mov     rdi, rcx
0x1004681eb  mov     [rsp+0F8h+var_D8], 0
0x1004681f0  call    cs:__imp_GetCurrentThreadId
0x1004681f6  cmp     esi, eax
0x1004681f8  jz      loc_100468584
0x1004681fe  mov     r13d, 1
0x100468204  mov     eax, r13d
0x100468207  xchg    al, [rdi]
0x100468209  test    al, al
0x10046820b  jnz     loc_100468584
0x100468211  xor     ebx, ebx
0x100468213  mov     [rsp+0F8h+lpBaseAddress], rbx
0x100468218  mov     [rsp+0F8h+var_C0], rbx
0x10046821d  mov     [rdi+4], r13d
0x100468221  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100468228  cmp     [rax], ebx
0x10046822a  jz      short loc_100468244
0x10046822c  lea     rcx, [rsp+0F8h+PerformanceCount]; lpPerformanceCount
0x100468234  call    cs:__imp_QueryPerformanceCounter
0x10046823a  mov     rax, qword ptr [rsp+0F8h+PerformanceCount]
0x100468242  jmp     short loc_100468251
0x100468244  mov     rax, ds:7FFE0008h
0x10046824c  mov     rbx, [rsp+0F8h+lpBaseAddress]
0x100468251  mov     [rsp+0F8h+var_B8], rax
0x100468256  mov     [rdi+8], rax
0x10046825a  mov     r8d, esi; dwThreadId
0x10046825d  xor     edx, edx; bInheritHandle
0x10046825f  lea     ecx, [rdx+4Ah]; dwDesiredAccess
0x100468262  call    cs:__imp_OpenThread
0x100468268  mov     r14, rax
0x10046826b  mov     [rsp+0F8h+var_70], rax
0x100468273  test    rax, rax
0x100468276  jz      loc_100468495
0x10046827c  mov     dword ptr [rdi+4], 2
0x100468283  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10046828a  cmp     dword ptr [rcx], 0
0x10046828d  jz      short loc_1004682A1
0x10046828f  lea     rcx, [rsp+0F8h+var_B0]; lpPerformanceCount
0x100468294  call    cs:__imp_QueryPerformanceCounter
0x10046829a  mov     rcx, qword ptr [rsp+0F8h+var_B0]
0x10046829f  jmp     short loc_1004682AE
0x1004682a1  mov     rcx, ds:7FFE0008h
0x1004682a9  mov     rbx, [rsp+0F8h+lpBaseAddress]
0x1004682ae  mov     [rsp+0F8h+var_A8], rcx
0x1004682b3  mov     [rdi+8], rcx
0x1004682b7  mov     rcx, r14; hThread
0x1004682ba  call    cs:__imp_SuspendThread
0x1004682c0  cmp     eax, 0FFFFFFFFh
0x1004682c3  jz      loc_100468495
0x1004682c9  mov     dword ptr [rdi+60h], 10000Bh
0x1004682d0  mov     dword ptr [rdi+4], 3
0x1004682d7  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004682de  mov     ecx, [rax]
0x1004682e0  mov     [rsp+0F8h+arg_18], ecx
0x1004682e7  test    ecx, ecx
0x1004682e9  jz      short loc_100468302
0x1004682eb  lea     rcx, [rsp+0F8h+var_A0]; lpPerformanceCount
0x1004682f0  call    cs:__imp_QueryPerformanceCounter
0x1004682f6  mov     rax, qword ptr [rsp+0F8h+var_A0]
0x1004682fb  mov     [rsp+0F8h+var_98], rax
0x100468300  jmp     short loc_100468314
0x100468302  mov     rax, ds:7FFE0008h
0x10046830a  mov     [rsp+0F8h+var_98], rax
0x10046830f  mov     rbx, [rsp+0F8h+lpBaseAddress]
0x100468314  mov     [rdi+8], rax
0x100468318  lea     rdx, [rdi+30h]; lpContext
0x10046831c  mov     rcx, r14; hThread
0x10046831f  call    cs:__imp_GetThreadContext
0x100468325  test    eax, eax
0x100468327  jz      loc_100468469
0x10046832d  lea     rax, [rdi+0C8h]
0x100468334  mov     [rsp+0F8h+var_C0], rax
0x100468339  mov     rbx, [rax]
0x10046833c  mov     [rsp+0F8h+lpBaseAddress], rbx
0x100468341  mov     dword ptr [rdi+4], 4
0x100468348  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10046834f  mov     ecx, [rax]
0x100468351  mov     [rsp+0F8h+arg_28], ecx
0x100468358  test    ecx, ecx
0x10046835a  jz      short loc_100468373
0x10046835c  lea     rcx, [rsp+0F8h+var_90]; lpPerformanceCount
0x100468361  call    cs:__imp_QueryPerformanceCounter
0x100468367  mov     rax, qword ptr [rsp+0F8h+var_90]
0x10046836c  mov     [rsp+0F8h+var_88], rax
0x100468371  jmp     short loc_100468385
0x100468373  mov     rax, ds:7FFE0008h
0x10046837b  mov     [rsp+0F8h+var_88], rax
0x100468380  mov     rbx, [rsp+0F8h+lpBaseAddress]
0x100468385  mov     [rdi+8], rax
0x100468389  mov     r8d, 30h ; '0'; dwLength
0x10046838f  lea     rdx, [rsp+0F8h+Buffer]; lpBuffer
0x100468397  mov     rcx, rbx; lpAddress
0x10046839a  call    cs:__imp_VirtualQuery
0x1004683a0  test    rax, rax
0x1004683a3  jz      loc_100468469
0x1004683a9  cmp     [rsp+0F8h+Buffer.AllocationProtect], 4
0x1004683b1  jnz     loc_100468469
0x1004683b7  mov     rsi, [rsp+0F8h+Buffer.BaseAddress]
0x1004683bf  sub     rsi, rbx
0x1004683c2  add     rsi, [rsp+0F8h+Buffer.RegionSize]
0x1004683ca  mov     [rsp+0F8h+nSize], rsi
0x1004683cf  cmp     rsi, r15
0x1004683d2  cmova   rsi, r15
0x1004683d6  mov     [rsp+0F8h+nSize], rsi
0x1004683db  mov     [rdi+18h], r12
0x1004683df  mov     [rdi+20h], rsi
0x1004683e3  mov     dword ptr [rdi+4], 5
0x1004683ea  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004683f1  mov     ecx, [rax]
0x1004683f3  mov     dword ptr [rsp+0F8h+arg_20], ecx
0x1004683fa  test    ecx, ecx
0x1004683fc  jz      short loc_100468418
0x1004683fe  lea     rcx, [rsp+0F8h+var_80]; lpPerformanceCount
0x100468403  call    cs:__imp_QueryPerformanceCounter
0x100468409  mov     rax, qword ptr [rsp+0F8h+var_80]
0x10046840e  mov     [rsp+0F8h+var_78], rax
0x100468416  jmp     short loc_100468432
0x100468418  mov     rax, ds:7FFE0008h
0x100468420  mov     [rsp+0F8h+var_78], rax
0x100468428  mov     rbx, [rsp+0F8h+lpBaseAddress]
0x10046842d  mov     rsi, [rsp+0F8h+nSize]
0x100468432  mov     [rdi+8], rax
0x100468436  test    sil, 7
0x10046843a  jnz     short loc_10046846E
0x10046843c  lfence
0x10046843f  mov     rsi, [rsp+0F8h+nSize]
0x100468444  mov     r8, rsi; nSize
0x100468447  mov     rbx, [rsp+0F8h+lpBaseAddress]
0x10046844c  mov     rdx, rbx; lpBaseAddress
0x10046844f  mov     rcx, [rdi+18h]; lpBuffer
0x100468453  call    ?DmpCopyMemorySafely@@YAJPEAXPEBX_K@Z; DmpCopyMemorySafely(void *,void const *,unsigned __int64)
0x100468458  movzx   ecx, [rsp+0F8h+var_D8]
0x10046845d  test    eax, eax
0x10046845f  cmovz   ecx, r13d
0x100468463  mov     [rsp+0F8h+var_D8], cl
0x100468467  jmp     short loc_10046846E
0x100468469  mov     rsi, [rsp+0F8h+nSize]
0x10046846e  jmp     short loc_10046848A
0x100468470  mov     rdi, [rsp+0F8h+arg_0]
0x100468478  mov     rbx, [rsp+0F8h+lpBaseAddress]
0x10046847d  mov     r14, [rsp+0F8h+var_70]
0x100468485  mov     rsi, [rsp+0F8h+nSize]
0x10046848a  mov     rcx, r14; hThread
0x10046848d  call    cs:__imp_ResumeThread
0x100468493  jmp     short loc_10046849A
0x100468495  mov     rsi, [rsp+0F8h+nSize]
0x10046849a  cmp     [rsp+0F8h+var_D8], 0
0x10046849f  jnz     short loc_1004684B2
0x1004684a1  call    cs:__imp_GetLastError
0x1004684a7  mov     [rdi+10h], eax
0x1004684aa  mov     byte ptr [rdi], 0
0x1004684ad  jmp     loc_100468576
0x1004684b2  mov     [rdi+9D0h], rbx
0x1004684b9  mov     r8, [rdi+18h]
0x1004684bd  sub     r8, rbx
0x1004684c0  mov     rax, [rsp+0F8h+var_C0]
0x1004684c5  add     [rax], r8
0x1004684c8  mov     rdx, [rdi+18h]
0x1004684cc  lea     rax, [rdx+rsi]
0x1004684d0  cmp     rdx, rax
0x1004684d3  jnb     short loc_1004684FF
0x1004684d5  mov     rcx, [rdx]
0x1004684d8  cmp     rcx, rbx
0x1004684db  jb      short loc_1004684EF
0x1004684dd  mov     rax, rcx
0x1004684e0  sub     rax, rbx
0x1004684e3  cmp     rax, rsi
0x1004684e6  ja      short loc_1004684EF
0x1004684e8  lea     rax, [rcx+r8]
0x1004684ec  mov     [rdx], rax
0x1004684ef  add     rdx, 8
0x1004684f3  mov     rcx, [rdi+18h]
0x1004684f7  add     rcx, rsi
0x1004684fa  cmp     rdx, rcx
0x1004684fd  jb      short loc_1004684D5
0x1004684ff  lea     r9, [rdi+500h]
0x100468506  lea     rcx, [rdi+30h]
0x10046850a  cmp     rcx, r9
0x10046850d  jnb     short loc_100468533
0x10046850f  nop
0x100468510  mov     rdx, [rcx]
0x100468513  cmp     rdx, rbx
0x100468516  jb      short loc_10046852A
0x100468518  mov     rax, rdx
0x10046851b  sub     rax, rbx
0x10046851e  cmp     rax, rsi
0x100468521  ja      short loc_10046852A
0x100468523  lea     rax, [rdx+r8]
0x100468527  mov     [rcx], rax
0x10046852a  add     rcx, 8
0x10046852e  cmp     rcx, r9
0x100468531  jb      short loc_100468510
0x100468533  mov     dword ptr [rdi+4], 6
0x10046853a  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100468541  cmp     dword ptr [rax], 0
0x100468544  jz      short loc_10046855E
0x100468546  lea     rcx, [rsp+0F8h+var_68]; lpPerformanceCount
0x10046854e  call    cs:__imp_QueryPerformanceCounter
0x100468554  mov     rax, qword ptr [rsp+0F8h+var_68]
0x10046855c  jmp     short loc_100468566
0x10046855e  mov     rax, ds:7FFE0008h
0x100468566  mov     [rdi+8], rax
0x10046856a  lea     rcx, aFailedToCollec; "Failed to collect non yield stack frame"...
0x100468571  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x100468576  test    r14, r14
0x100468579  jz      short loc_100468584
0x10046857b  mov     rcx, r14; hObject
0x10046857e  call    cs:__imp_CloseHandle
0x100468584  movzx   eax, [rsp+0F8h+var_D8]
0x100468589  lea     r11, [rsp+0F8h+var_28]
0x100468591  mov     rbx, [r11+38h]
0x100468595  mov     rsi, [r11+40h]
0x100468599  mov     rsp, r11
0x10046859c  pop     r15
0x10046859e  pop     r14
0x1004685a0  pop     r13
0x1004685a2  pop     r12
0x1004685a4  pop     rdi
0x1004685a5  retn
```
