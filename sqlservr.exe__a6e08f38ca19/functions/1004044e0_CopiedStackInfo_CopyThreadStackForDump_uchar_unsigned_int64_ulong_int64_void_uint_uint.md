# CopiedStackInfo::CopyThreadStackForDump(uchar *,unsigned __int64,ulong,__int64 (**)(void),uint,uint &)

- ea: `0x1004044e0`
- end: `0x1004048ec`
- name: `?CopyThreadStackForDump@CopiedStackInfo@@QEAA_NPEAE_KKPEAP6A_JXZIAEAI@Z`
- size: `1036`
- prototype: `bool(CopiedStackInfo *__hidden this, unsigned __int8 *, unsigned __int64, unsigned int, __int64 (**)(void), unsigned int, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x100405b20`
- `0x100406350`
- `0x100406750`
- `0x100406c30`

## callees

- `0x1004044e0`
- `0x1004404f0`
- `0x100441050`

## import_xrefs

- `KERNEL32!GetThreadContext` at `0x100404639`
- `KERNEL32!GetThreadContext` at `0x100404639`
- `KERNEL32!CloseHandle` at `0x1004048c4`
- `KERNEL32!CloseHandle` at `0x1004048c4`
- `KERNEL32!GetLastError` at `0x1004047c1`
- `KERNEL32!GetLastError` at `0x1004047c1`
- `KERNEL32!ResumeThread` at `0x1004047ad`
- `KERNEL32!ResumeThread` at `0x1004047ad`
- `KERNEL32!SuspendThread` at `0x1004045d4`
- `KERNEL32!SuspendThread` at `0x1004045d4`
- `KERNEL32!GetCurrentThreadId` at `0x100404510`
- `KERNEL32!GetCurrentThreadId` at `0x100404510`
- `KERNEL32!OpenThread` at `0x10040457c`
- `KERNEL32!OpenThread` at `0x10040457c`
- `KERNEL32!VirtualQuery` at `0x1004046b7`
- `KERNEL32!VirtualQuery` at `0x1004046b7`
- `KERNEL32!QueryPerformanceCounter` at `0x100404551`
- `KERNEL32!QueryPerformanceCounter` at `0x1004045ae`
- `KERNEL32!QueryPerformanceCounter` at `0x10040460a`
- `KERNEL32!QueryPerformanceCounter` at `0x100404678`
- `KERNEL32!QueryPerformanceCounter` at `0x100404720`
- `KERNEL32!QueryPerformanceCounter` at `0x100404870`
- `KERNEL32!QueryPerformanceCounter` at `0x100404551`
- `KERNEL32!QueryPerformanceCounter` at `0x1004045ae`
- `KERNEL32!QueryPerformanceCounter` at `0x10040460a`
- `KERNEL32!QueryPerformanceCounter` at `0x100404678`
- `KERNEL32!QueryPerformanceCounter` at `0x100404720`
- `KERNEL32!QueryPerformanceCounter` at `0x100404870`
- `sqllang!?CollectStackFramesFromContext@@YA_NPEBU_CONTEXT@@IPEAPEAXAEAI@Z` at `0x1004048a6`
- `sqllang!?CollectStackFramesFromContext@@YA_NPEBU_CONTEXT@@IPEAPEAXAEAI@Z` at `0x1004048a6`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100404541`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040459d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004045f1`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100404662`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100404707`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040485c`

## pseudocode

```c
_BOOL8 __fastcall CopiedStackInfo::CopyThreadStackForDump(
        CopiedStackInfo *this,
        unsigned __int8 *a2,
        SIZE_T a3,
        DWORD a4,
        __int64 (**a5)(void),
        unsigned int a6,
        unsigned int *a7)
{
  char v11; // al
  void *v12; // rbx
  LARGE_INTEGER v13; // rax
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
  bool v27; // [rsp+20h] [rbp-E8h]
  SIZE_T nSize; // [rsp+30h] [rbp-D8h]
  _QWORD *v29; // [rsp+38h] [rbp-D0h]
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-C0h] BYREF
  LARGE_INTEGER v31; // [rsp+50h] [rbp-B8h]
  LARGE_INTEGER v32; // [rsp+58h] [rbp-B0h] BYREF
  LARGE_INTEGER v33; // [rsp+60h] [rbp-A8h]
  LARGE_INTEGER v34; // [rsp+68h] [rbp-A0h] BYREF
  LARGE_INTEGER v35; // [rsp+70h] [rbp-98h]
  LARGE_INTEGER v36; // [rsp+78h] [rbp-90h] BYREF
  LARGE_INTEGER v37; // [rsp+80h] [rbp-88h]
  LARGE_INTEGER v38; // [rsp+88h] [rbp-80h] BYREF
  LARGE_INTEGER v39; // [rsp+90h] [rbp-78h]
  HANDLE v40; // [rsp+98h] [rbp-70h]
  LARGE_INTEGER v41; // [rsp+A0h] [rbp-68h] BYREF
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+A8h] [rbp-60h] BYREF

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
        QueryPerformanceCounter(&PerformanceCount);
        v13 = PerformanceCount;
      }
      else
      {
        v13.QuadPart = MEMORY[0x7FFE0008];
        v12 = 0;
      }
      v31 = v13;
      *((LARGE_INTEGER *)this + 1) = v13;
      v14 = OpenThread(0x4Au, 0, a4);
      v40 = v14;
      if ( !v14
        || ((*((_DWORD *)this + 1) = 2, !Base_PublicGlobals::sm_invariantTscAvailable)
          ? (v15.QuadPart = MEMORY[0x7FFE0008], v12 = 0)
          : (void *)(QueryPerformanceCounter(&v32), v15 = v32),
            v33 = v15,
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
          QueryPerformanceCounter(&v34);
          v16 = v34;
          v35 = v34;
        }
        else
        {
          v16.QuadPart = MEMORY[0x7FFE0008];
          v35.QuadPart = MEMORY[0x7FFE0008];
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
          QueryPerformanceCounter(&v36);
          v17 = v36;
          v37 = v36;
        }
        else
        {
          v17.QuadPart = MEMORY[0x7FFE0008];
          v37.QuadPart = MEMORY[0x7FFE0008];
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
            QueryPerformanceCounter(&v38);
            v19 = v38;
            v39 = v38;
          }
          else
          {
            v19.QuadPart = MEMORY[0x7FFE0008];
            v39.QuadPart = MEMORY[0x7FFE0008];
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
          QueryPerformanceCounter(&v41);
          v25 = v41;
        }
        else
        {
          v25.QuadPart = MEMORY[0x7FFE0008];
        }
        *((LARGE_INTEGER *)this + 1) = v25;
        if ( !CollectStackFramesFromContext((const struct _CONTEXT *)((char *)this + 48), a6, (void **)a5, a7) )
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
0x1004044e0  mov     [rsp+arg_8], rbx
0x1004044e5  mov     [rsp+arg_10], rsi
0x1004044ea  mov     [rsp+arg_0], rcx
0x1004044ef  push    rdi
0x1004044f0  push    r12
0x1004044f2  push    r13
0x1004044f4  push    r14
0x1004044f6  push    r15
0x1004044f8  sub     rsp, 0E0h
0x1004044ff  mov     esi, r9d
0x100404502  mov     r15, r8
0x100404505  mov     r12, rdx
0x100404508  mov     rdi, rcx
0x10040450b  mov     [rsp+108h+var_E8], 0
0x100404510  call    cs:__imp_GetCurrentThreadId
0x100404516  cmp     esi, eax
0x100404518  jz      loc_1004048CA
0x10040451e  mov     r13d, 1
0x100404524  mov     eax, r13d
0x100404527  xchg    al, [rdi]
0x100404529  test    al, al
0x10040452b  jnz     loc_1004048CA
0x100404531  xor     ebx, ebx
0x100404533  mov     [rsp+108h+lpBaseAddress], rbx
0x100404538  mov     [rsp+108h+var_D0], rbx
0x10040453d  mov     [rdi+4], r13d
0x100404541  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100404548  cmp     [rax], ebx
0x10040454a  jz      short loc_10040455E
0x10040454c  lea     rcx, [rsp+108h+PerformanceCount]; lpPerformanceCount
0x100404551  call    cs:__imp_QueryPerformanceCounter
0x100404557  mov     rax, qword ptr [rsp+108h+PerformanceCount]
0x10040455c  jmp     short loc_10040456B
0x10040455e  mov     rax, ds:7FFE0008h
0x100404566  mov     rbx, [rsp+108h+lpBaseAddress]
0x10040456b  mov     [rsp+108h+var_B8], rax
0x100404570  mov     [rdi+8], rax
0x100404574  mov     r8d, esi; dwThreadId
0x100404577  xor     edx, edx; bInheritHandle
0x100404579  lea     ecx, [rdx+4Ah]; dwDesiredAccess
0x10040457c  call    cs:__imp_OpenThread
0x100404582  mov     r14, rax
0x100404585  mov     [rsp+108h+var_70], rax
0x10040458d  test    rax, rax
0x100404590  jz      loc_1004047B5
0x100404596  mov     dword ptr [rdi+4], 2
0x10040459d  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004045a4  cmp     dword ptr [rcx], 0
0x1004045a7  jz      short loc_1004045BB
0x1004045a9  lea     rcx, [rsp+108h+var_B0]; lpPerformanceCount
0x1004045ae  call    cs:__imp_QueryPerformanceCounter
0x1004045b4  mov     rcx, qword ptr [rsp+108h+var_B0]
0x1004045b9  jmp     short loc_1004045C8
0x1004045bb  mov     rcx, ds:7FFE0008h
0x1004045c3  mov     rbx, [rsp+108h+lpBaseAddress]
0x1004045c8  mov     [rsp+108h+var_A8], rcx
0x1004045cd  mov     [rdi+8], rcx
0x1004045d1  mov     rcx, r14; hThread
0x1004045d4  call    cs:__imp_SuspendThread
0x1004045da  cmp     eax, 0FFFFFFFFh
0x1004045dd  jz      loc_1004047B5
0x1004045e3  mov     dword ptr [rdi+60h], 10000Bh
0x1004045ea  mov     dword ptr [rdi+4], 3
0x1004045f1  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004045f8  mov     ecx, [rax]
0x1004045fa  mov     [rsp+108h+arg_18], ecx
0x100404601  test    ecx, ecx
0x100404603  jz      short loc_10040461C
0x100404605  lea     rcx, [rsp+108h+var_A0]; lpPerformanceCount
0x10040460a  call    cs:__imp_QueryPerformanceCounter
0x100404610  mov     rax, qword ptr [rsp+108h+var_A0]
0x100404615  mov     [rsp+108h+var_98], rax
0x10040461a  jmp     short loc_10040462E
0x10040461c  mov     rax, ds:7FFE0008h
0x100404624  mov     [rsp+108h+var_98], rax
0x100404629  mov     rbx, [rsp+108h+lpBaseAddress]
0x10040462e  mov     [rdi+8], rax
0x100404632  lea     rdx, [rdi+30h]; lpContext
0x100404636  mov     rcx, r14; hThread
0x100404639  call    cs:__imp_GetThreadContext
0x10040463f  test    eax, eax
0x100404641  jz      loc_100404789
0x100404647  lea     rax, [rdi+0C8h]
0x10040464e  mov     [rsp+108h+var_D0], rax
0x100404653  mov     rbx, [rax]
0x100404656  mov     [rsp+108h+lpBaseAddress], rbx
0x10040465b  mov     dword ptr [rdi+4], 4
0x100404662  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100404669  mov     ecx, [rax]
0x10040466b  mov     [rsp+108h+var_C8], ecx
0x10040466f  test    ecx, ecx
0x100404671  jz      short loc_10040468D
0x100404673  lea     rcx, [rsp+108h+var_90]; lpPerformanceCount
0x100404678  call    cs:__imp_QueryPerformanceCounter
0x10040467e  mov     rax, qword ptr [rsp+108h+var_90]
0x100404683  mov     [rsp+108h+var_88], rax
0x10040468b  jmp     short loc_1004046A2
0x10040468d  mov     rax, ds:7FFE0008h
0x100404695  mov     [rsp+108h+var_88], rax
0x10040469d  mov     rbx, [rsp+108h+lpBaseAddress]
0x1004046a2  mov     [rdi+8], rax
0x1004046a6  mov     r8d, 30h ; '0'; dwLength
0x1004046ac  lea     rdx, [rsp+108h+Buffer]; lpBuffer
0x1004046b4  mov     rcx, rbx; lpAddress
0x1004046b7  call    cs:__imp_VirtualQuery
0x1004046bd  test    rax, rax
0x1004046c0  jz      loc_100404789
0x1004046c6  cmp     [rsp+108h+Buffer.AllocationProtect], 4
0x1004046ce  jnz     loc_100404789
0x1004046d4  mov     rsi, [rsp+108h+Buffer.BaseAddress]
0x1004046dc  sub     rsi, rbx
0x1004046df  add     rsi, [rsp+108h+Buffer.RegionSize]
0x1004046e7  mov     [rsp+108h+nSize], rsi
0x1004046ec  cmp     rsi, r15
0x1004046ef  cmova   rsi, r15
0x1004046f3  mov     [rsp+108h+nSize], rsi
0x1004046f8  mov     [rdi+18h], r12
0x1004046fc  mov     [rdi+20h], rsi
0x100404700  mov     dword ptr [rdi+4], 5
0x100404707  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040470e  mov     ecx, [rax]
0x100404710  mov     [rsp+108h+var_C4], ecx
0x100404714  test    ecx, ecx
0x100404716  jz      short loc_100404738
0x100404718  lea     rcx, [rsp+108h+var_80]; lpPerformanceCount
0x100404720  call    cs:__imp_QueryPerformanceCounter
0x100404726  mov     rax, qword ptr [rsp+108h+var_80]
0x10040472e  mov     [rsp+108h+var_78], rax
0x100404736  jmp     short loc_100404752
0x100404738  mov     rax, ds:7FFE0008h
0x100404740  mov     [rsp+108h+var_78], rax
0x100404748  mov     rbx, [rsp+108h+lpBaseAddress]
0x10040474d  mov     rsi, [rsp+108h+nSize]
0x100404752  mov     [rdi+8], rax
0x100404756  test    sil, 7
0x10040475a  jnz     short loc_10040478E
0x10040475c  lfence
0x10040475f  mov     rsi, [rsp+108h+nSize]
0x100404764  mov     r8, rsi; nSize
0x100404767  mov     rbx, [rsp+108h+lpBaseAddress]
0x10040476c  mov     rdx, rbx; lpBaseAddress
0x10040476f  mov     rcx, [rdi+18h]; lpBuffer
0x100404773  call    ?DmpCopyMemorySafely@@YAJPEAXPEBX_K@Z; DmpCopyMemorySafely(void *,void const *,unsigned __int64)
0x100404778  movzx   ecx, [rsp+108h+var_E8]
0x10040477d  test    eax, eax
0x10040477f  cmovz   ecx, r13d
0x100404783  mov     [rsp+108h+var_E8], cl
0x100404787  jmp     short loc_10040478E
0x100404789  mov     rsi, [rsp+108h+nSize]
0x10040478e  jmp     short loc_1004047AA
0x100404790  mov     rdi, [rsp+108h+arg_0]
0x100404798  mov     rbx, [rsp+108h+lpBaseAddress]
0x10040479d  mov     r14, [rsp+108h+var_70]
0x1004047a5  mov     rsi, [rsp+108h+nSize]
0x1004047aa  mov     rcx, r14; hThread
0x1004047ad  call    cs:__imp_ResumeThread
0x1004047b3  jmp     short loc_1004047BA
0x1004047b5  mov     rsi, [rsp+108h+nSize]
0x1004047ba  cmp     [rsp+108h+var_E8], 0
0x1004047bf  jnz     short loc_1004047D2
0x1004047c1  call    cs:__imp_GetLastError
0x1004047c7  mov     [rdi+10h], eax
0x1004047ca  mov     byte ptr [rdi], 0
0x1004047cd  jmp     loc_1004048BC
0x1004047d2  mov     [rdi+9D0h], rbx
0x1004047d9  mov     r8, [rdi+18h]
0x1004047dd  sub     r8, rbx
0x1004047e0  mov     rax, [rsp+108h+var_D0]
0x1004047e5  add     [rax], r8
0x1004047e8  mov     rdx, [rdi+18h]
0x1004047ec  lea     rax, [rdx+rsi]
0x1004047f0  cmp     rdx, rax
0x1004047f3  jnb     short loc_10040481F
0x1004047f5  mov     rcx, [rdx]
0x1004047f8  cmp     rcx, rbx
0x1004047fb  jb      short loc_10040480F
0x1004047fd  mov     rax, rcx
0x100404800  sub     rax, rbx
0x100404803  cmp     rax, rsi
0x100404806  ja      short loc_10040480F
0x100404808  lea     rax, [rcx+r8]
0x10040480c  mov     [rdx], rax
0x10040480f  add     rdx, 8
0x100404813  mov     rcx, [rdi+18h]
0x100404817  add     rcx, rsi
0x10040481a  cmp     rdx, rcx
0x10040481d  jb      short loc_1004047F5
0x10040481f  lea     r15, [rdi+30h]
0x100404823  lea     r9, [rdi+500h]
0x10040482a  mov     rcx, r15
0x10040482d  cmp     r15, r9
0x100404830  jnb     short loc_100404855
0x100404832  mov     rdx, [rcx]
0x100404835  cmp     rdx, rbx
0x100404838  jb      short loc_10040484C
0x10040483a  mov     rax, rdx
0x10040483d  sub     rax, rbx
0x100404840  cmp     rax, rsi
0x100404843  ja      short loc_10040484C
0x100404845  lea     rax, [rdx+r8]
0x100404849  mov     [rcx], rax
0x10040484c  add     rcx, 8
0x100404850  cmp     rcx, r9
0x100404853  jb      short loc_100404832
0x100404855  mov     dword ptr [rdi+4], 6
0x10040485c  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100404863  cmp     dword ptr [rax], 0
0x100404866  jz      short loc_100404880
0x100404868  lea     rcx, [rsp+108h+var_68]; lpPerformanceCount
0x100404870  call    cs:__imp_QueryPerformanceCounter
0x100404876  mov     rax, qword ptr [rsp+108h+var_68]
0x10040487e  jmp     short loc_100404888
0x100404880  mov     rax, ds:7FFE0008h
0x100404888  mov     [rdi+8], rax
0x10040488c  mov     r9, [rsp+108h+arg_30]
0x100404894  mov     r8, [rsp+108h+arg_20]
0x10040489c  mov     edx, [rsp+108h+arg_28]
0x1004048a3  mov     rcx, r15
0x1004048a6  call    cs:__imp_?CollectStackFramesFromContext@@YA_NPEBU_CONTEXT@@IPEAPEAXAEAI@Z; CollectStackFramesFromContext(_CONTEXT const *,uint,void * *,uint &)
0x1004048ac  test    al, al
0x1004048ae  jnz     short loc_1004048BC
0x1004048b0  lea     rcx, aFailedToCollec; "Failed to collect non yield stack frame"...
0x1004048b7  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x1004048bc  test    r14, r14
0x1004048bf  jz      short loc_1004048CA
0x1004048c1  mov     rcx, r14; hObject
0x1004048c4  call    cs:__imp_CloseHandle
0x1004048ca  movzx   eax, [rsp+108h+var_E8]
0x1004048cf  lea     r11, [rsp+108h+var_28]
0x1004048d7  mov     rbx, [r11+38h]
0x1004048db  mov     rsi, [r11+40h]
0x1004048df  mov     rsp, r11
0x1004048e2  pop     r15
0x1004048e4  pop     r14
0x1004048e6  pop     r13
0x1004048e8  pop     r12
0x1004048ea  pop     rdi
0x1004048eb  retn
```
