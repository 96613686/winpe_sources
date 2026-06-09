# CWebPlatStorageCom::GetRPCEndpoint(ushort * *)

- ea: `0x180046800`
- end: `0x180046b6b`
- name: `?GetRPCEndpoint@CWebPlatStorageCom@@UEAAJPEAPEAG@Z`
- size: `875`
- prototype: `__int64 __fastcall(CWebPlatStorageCom *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180046800`
- `0x180046b74`
- `0x180046f04`
- `0x180046f20`
- `0x1800473c0`
- `0x180054c54`
- `0x180075ba4`
- `0x180081b40`
- `0x18008cab4`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046889`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046889`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800468d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004692c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800468d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004692c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800468ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004696d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800468ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004696d`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180046941`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180046b04`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180046941`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180046b04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800469b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800469b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046b60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046b60`

## pseudocode

```c
__int64 __fastcall CWebPlatStorageCom::GetRPCEndpoint(CWebPlatStorageCom *this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rsi
  int started; // edi
  void *v7; // rbx
  int v8; // esi
  int v9; // edx
  unsigned int v10; // r8d
  unsigned __int16 *v11; // r15
  __int64 v12; // rdi
  unsigned __int16 *v13; // rbx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r14
  unsigned __int16 *v16; // rcx
  signed int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rax
  unsigned __int16 *v21; // rcx
  unsigned __int16 v22; // r8
  void *v23; // [rsp+28h] [rbp-28h] BYREF
  __int64 v24; // [rsp+30h] [rbp-20h]
  _QWORD v25[3]; // [rsp+38h] [rbp-18h] BYREF

  HIDWORD(v23) = 0;
  v4 = (unsigned __int16 *)&qword_1800D76F0;
  v25[0] = &qword_1800D76F0;
  v25[1] = 0;
  if ( a2 )
    *a2 = 0;
  started = CWebPlatStorageCom::InitializeWebPlatStorageServer(this);
  if ( started < 0 )
  {
    HIDWORD(v23) = 129;
    goto LABEL_7;
  }
  v7 = (void *)*((_QWORD *)this + 4);
  v23 = v7;
  v8 = 0;
  v24 = 0;
  CWxString::Empty((CWxString *)v25);
  if ( v7 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)v7);
    v8 = 1;
    LODWORD(v24) = 1;
  }
  while ( *((_DWORD *)v7 + 12) )
  {
    if ( *((_DWORD *)v7 + 12) == 3 )
      goto LABEL_19;
    started = WxSleepConditionVariable(
                (struct _RTL_CONDITION_VARIABLE *)v7 + 5,
                (struct _RTL_CRITICAL_SECTION *)v7,
                v10);
    if ( started < 0 )
      goto LABEL_20;
  }
  *((_DWORD *)v7 + 12) = 2;
  if ( v8 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)v7);
    LODWORD(v24) = 0;
  }
  started = CWebPlatStorageServer::StartRpcServer((CWebPlatStorageServer *)v7, v9);
  if ( started >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)v7);
    v8 = 1;
    *((_DWORD *)v7 + 12) = 3;
    WakeAllConditionVariable((PCONDITION_VARIABLE)v7 + 5);
LABEL_19:
    started = CWxString::Set((CWxString *)v25, *((const unsigned __int16 **)v7 + 19));
    goto LABEL_20;
  }
  AutoCritSec::Lock((AutoCritSec *)&v23);
  *((_DWORD *)v7 + 12) = 0;
  WakeAllConditionVariable((PCONDITION_VARIABLE)v7 + 5);
  v8 = v24;
  v7 = v23;
LABEL_20:
  if ( v8 && v7 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v7);
  v4 = (unsigned __int16 *)v25[0];
  if ( started < 0 )
  {
    HIDWORD(v23) = 130;
    goto LABEL_7;
  }
  v11 = 0;
  if ( v25[0] )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(v25[0] + 2 * v12) );
    v13 = 0;
    v23 = 0;
    v14 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)(2 * v12 + 2));
    v15 = v14;
    if ( !v14 )
    {
      started = -2147024882;
      goto LABEL_34;
    }
    memset_0(v14, 0, (unsigned int)(2 * v12 + 2));
    v13 = v15;
    v23 = v15;
    v18 = v12 + 1;
    v19 = (unsigned int)(v12 + 1);
    started = -2147024809;
    if ( v18 )
    {
      if ( v18 <= 0x7FFFFFFFuLL )
      {
        v20 = 2147483646;
        v21 = v4;
        do
        {
          if ( !v20 )
            break;
          v22 = *v21;
          if ( !*v21 )
            break;
          ++v21;
          *v15++ = v22;
          --v20;
          --v19;
        }
        while ( v19 );
        v16 = v15 - 1;
        if ( v19 )
          v16 = v15;
        *v16 = 0;
        v17 = v19 == 0 ? 0x8007007A : 0;
        goto LABEL_32;
      }
    }
    else
    {
      v17 = -2147024809;
      if ( !v19 )
      {
LABEL_32:
        started = v17;
        if ( v17 >= 0 )
        {
          v11 = v13;
          v13 = 0;
          v23 = 0;
        }
        goto LABEL_34;
      }
    }
    *v15 = 0;
LABEL_34:
    if ( v13 )
      WxCoTaskAllocator::Free(&v23);
    goto LABEL_36;
  }
  started = -2147024809;
LABEL_36:
  if ( started < 0 )
  {
    HIDWORD(v23) = 131;
    if ( v11 )
      CoTaskMemFree(v11);
  }
  else
  {
    *a2 = v11;
  }
LABEL_7:
  if ( v4 != &qword_1800D76F0 && v4 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v4);
    else
      HeapFree(g_hWxProcessHeap, 0, v4);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180046800  mov     [rsp-38h+arg_10], rbx
0x180046805  push    rbp
0x180046806  push    rsi
0x180046807  push    rdi
0x180046808  push    r12
0x18004680a  push    r13
0x18004680c  push    r14
0x18004680e  push    r15
0x180046810  mov     rbp, rsp
0x180046813  sub     rsp, 50h
0x180046817  mov     r13, rdx
0x18004681a  mov     rbx, rcx
0x18004681d  xor     r12d, r12d
0x180046820  mov     dword ptr [rbp+var_28+4], r12d
0x180046824  lea     rsi, qword_1800D76F0
0x18004682b  mov     [rbp+var_18], rsi
0x18004682f  mov     [rbp+var_10], r12
0x180046833  test    rdx, rdx
0x180046836  jz      short loc_18004683B
0x180046838  mov     [rdx], r12
0x18004683b  call    ?InitializeWebPlatStorageServer@CWebPlatStorageCom@@QEAAJXZ; CWebPlatStorageCom::InitializeWebPlatStorageServer(void)
0x180046840  mov     edi, eax
0x180046842  test    eax, eax
0x180046844  jns     short loc_1800468AA
0x180046846  mov     dword ptr [rbp+var_28+4], 81h
0x18004684d  jmp     short loc_18004685F
0x18004684f  mov     dword ptr [rbp+var_28+4], 83h
0x180046856  test    r15, r15
0x180046859  jnz     loc_180046B5D
0x18004685f  lea     rax, qword_1800D76F0
0x180046866  cmp     rsi, rax
0x180046869  jz      short loc_180046890
0x18004686b  test    rsi, rsi
0x18004686e  jz      short loc_180046890
0x180046870  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r12d; int g_fWxHeapExtensionInitialized
0x180046877  jnz     loc_180046AAA
0x18004687d  mov     r8, rsi; lpMem
0x180046880  xor     edx, edx; dwFlags
0x180046882  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180046889  call    cs:__imp_HeapFree
0x18004688f  nop
0x180046890  mov     eax, edi
0x180046892  mov     rbx, [rsp+50h+arg_10]
0x18004689a  add     rsp, 50h
0x18004689e  pop     r15
0x1800468a0  pop     r14
0x1800468a2  pop     r13
0x1800468a4  pop     r12
0x1800468a6  pop     rdi
0x1800468a7  pop     rsi
0x1800468a8  pop     rbp
0x1800468a9  retn
0x1800468aa  mov     rbx, [rbx+20h]
0x1800468ae  mov     [rbp+var_2C], r12d
0x1800468b2  mov     [rbp+var_20], r12
0x1800468b6  mov     [rbp-28h], rbx
0x1800468ba  mov     esi, r12d
0x1800468bd  mov     dword ptr [rbp+var_20], r12d
0x1800468c1  lea     rcx, [rbp+var_18]; this
0x1800468c5  call    ?Empty@CWxString@@QEAAXXZ; CWxString::Empty(void)
0x1800468ca  test    rbx, rbx
0x1800468cd  jz      short loc_1800468E0
0x1800468cf  mov     rcx, rbx; lpCriticalSection
0x1800468d2  call    cs:__imp_EnterCriticalSection
0x1800468d8  mov     esi, 1
0x1800468dd  mov     dword ptr [rbp+var_20], esi
0x1800468e0  lea     r14, [rbx+28h]
0x1800468e4  mov     r15, r14
0x1800468e7  cmp     [rbx+30h], r12d
0x1800468eb  jnz     loc_180046ABE
0x1800468f1  mov     dword ptr [rbx+30h], 2
0x1800468f8  test    esi, esi
0x1800468fa  jz      short loc_18004690F
0x1800468fc  mov     rcx, rbx; lpCriticalSection
0x1800468ff  call    cs:__imp_LeaveCriticalSection
0x180046905  mov     esi, r12d
0x180046908  mov     dword ptr [rbp+var_20], r12d
0x18004690c  mov     r15, r14
0x18004690f  mov     rcx, rbx; this
0x180046912  call    ?StartRpcServer@CWebPlatStorageServer@@AEAAJH@Z; CWebPlatStorageServer::StartRpcServer(int)
0x180046917  mov     edi, eax
0x180046919  test    eax, eax
0x18004691b  js      loc_180046AED
0x180046921  test    esi, esi
0x180046923  jnz     loc_180046B16
0x180046929  mov     rcx, rbx; lpCriticalSection
0x18004692c  call    cs:__imp_EnterCriticalSection
0x180046932  mov     esi, 1
0x180046937  mov     dword ptr [rbx+30h], 3
0x18004693e  mov     rcx, r14; ConditionVariable
0x180046941  call    cs:__imp_WakeAllConditionVariable
0x180046947  mov     rdx, [rbx+98h]; unsigned __int16 *
0x18004694e  lea     rcx, [rbp+var_18]; this
0x180046952  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x180046957  mov     edi, eax
0x180046959  test    eax, eax
0x18004695b  js      loc_180046B1E
0x180046961  test    esi, esi
0x180046963  jz      short loc_180046973
0x180046965  test    rbx, rbx
0x180046968  jz      short loc_180046973
0x18004696a  mov     rcx, rbx; lpCriticalSection
0x18004696d  call    cs:__imp_LeaveCriticalSection
0x180046973  mov     rsi, [rbp+var_18]
0x180046977  test    edi, edi
0x180046979  js      loc_180046A8F
0x18004697f  mov     [rbp+var_2C], r12d
0x180046983  mov     r15, r12
0x180046986  test    rsi, rsi
0x180046989  jz      loc_180046B2A
0x18004698f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180046993  inc     rdi
0x180046996  cmp     [rsi+rdi*2], r12w
0x18004699b  jnz     short loc_180046993
0x18004699d  mov     [rbp+var_2C], r12d
0x1800469a1  mov     rbx, r12
0x1800469a4  mov     [rbp-28h], rbx
0x1800469a8  lea     eax, ds:2[rdi*2]
0x1800469af  mov     r12d, eax
0x1800469b2  mov     ecx, eax; cb
0x1800469b4  call    cs:__imp_CoTaskMemAlloc
0x1800469ba  mov     r14, rax
0x1800469bd  test    rax, rax
0x1800469c0  jnz     short loc_180046A20
0x1800469c2  mov     [rbp+var_2C], 4Ch ; 'L'
0x1800469c9  mov     edi, 8007000Eh
0x1800469ce  mov     [rbp+var_2C], 220h
0x1800469d5  xor     r12d, r12d
0x1800469d8  jmp     short loc_180046A06
0x1800469da  lea     rcx, [r14-2]
0x1800469de  test    rdx, rdx
0x1800469e1  cmovnz  rcx, r14
0x1800469e5  mov     [rcx], r12w
0x1800469e9  neg     rdx
0x1800469ec  sbb     eax, eax
0x1800469ee  not     eax
0x1800469f0  and     eax, 8007007Ah
0x1800469f5  mov     edi, eax
0x1800469f7  test    eax, eax
0x1800469f9  jns     loc_180046A9B
0x1800469ff  mov     [rbp+var_2C], 224h
0x180046a06  test    rbx, rbx
0x180046a09  jnz     loc_180046B4F
0x180046a0f  test    edi, edi
0x180046a11  js      loc_18004684F
0x180046a17  mov     [r13+0], r15
0x180046a1b  jmp     loc_18004685F
0x180046a20  mov     r8, r12; Size
0x180046a23  xor     edx, edx; Val
0x180046a25  mov     rcx, r14; void *
0x180046a28  call    memset_0
0x180046a2d  mov     rbx, r14
0x180046a30  mov     [rbp-28h], rbx
0x180046a34  lea     eax, [rdi+1]
0x180046a37  mov     edx, eax
0x180046a39  mov     edi, 80070057h
0x180046a3e  xor     r12d, r12d
0x180046a41  test    eax, eax
0x180046a43  jz      loc_180046B3B
0x180046a49  cmp     rdx, 7FFFFFFFh
0x180046a50  ja      loc_180046B46
0x180046a56  mov     eax, 7FFFFFFEh
0x180046a5b  mov     rcx, rsi
0x180046a5e  test    rax, rax
0x180046a61  jz      loc_1800469DA
0x180046a67  movzx   r8d, word ptr [rcx]
0x180046a6b  test    r8w, r8w
0x180046a6f  jz      loc_1800469DA
0x180046a75  add     rcx, 2
0x180046a79  mov     [r14], r8w
0x180046a7d  add     r14, 2
0x180046a81  dec     rax
0x180046a84  sub     rdx, 1
0x180046a88  jnz     short loc_180046A5E
0x180046a8a  jmp     loc_1800469DA
0x180046a8f  mov     dword ptr [rbp+var_28+4], 82h
0x180046a96  jmp     loc_18004685F
0x180046a9b  mov     r15, rbx
0x180046a9e  mov     rbx, r12
0x180046aa1  mov     [rbp-28h], rbx
0x180046aa5  jmp     loc_180046A06
0x180046aaa  mov     rcx, rsi
0x180046aad  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x180046ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ab9  jmp     loc_180046890
0x180046abe  cmp     dword ptr [rbx+30h], 3
0x180046ac2  jz      loc_180046947
0x180046ac8  lea     r15, [rbx+28h]
0x180046acc  mov     rdx, rbx; struct _RTL_CRITICAL_SECTION *
0x180046acf  mov     rcx, r15; struct _RTL_CONDITION_VARIABLE *
0x180046ad2  call    ?WxSleepConditionVariable@@YAJPEAU_RTL_CONDITION_VARIABLE@@PEAU_RTL_CRITICAL_SECTION@@K@Z; WxSleepConditionVariable(_RTL_CONDITION_VARIABLE *,_RTL_CRITICAL_SECTION *,ulong)
0x180046ad7  mov     edi, eax
0x180046ad9  test    eax, eax
0x180046adb  jns     loc_1800468E7
0x180046ae1  mov     [rbp+var_2C], 177h
0x180046ae8  jmp     loc_180046961
0x180046aed  mov     [rbp+var_2C], 190h
0x180046af4  lea     rcx, [rbp+var_28]; this
0x180046af8  call    ?Lock@AutoCritSec@@QEAAXXZ; AutoCritSec::Lock(void)
0x180046afd  mov     [rbx+30h], r12d
0x180046b01  mov     rcx, r14; ConditionVariable
0x180046b04  call    cs:__imp_WakeAllConditionVariable
0x180046b0a  mov     esi, dword ptr [rbp+var_20]
0x180046b0d  mov     rbx, [rbp+var_28]
0x180046b11  jmp     loc_180046961
0x180046b16  mov     r14, r15
0x180046b19  jmp     loc_180046937
0x180046b1e  mov     [rbp+var_2C], 1A2h
0x180046b25  jmp     loc_180046961
0x180046b2a  mov     [rbp+var_2C], 21Ah
0x180046b31  mov     edi, 80070057h
0x180046b36  jmp     loc_180046A0F
0x180046b3b  mov     eax, edi
0x180046b3d  test    rdx, rdx
0x180046b40  jz      loc_1800469F5
0x180046b46  mov     [r14], r12w
0x180046b4a  jmp     loc_1800469FF
0x180046b4f  lea     rcx, [rbp+var_28]; void **
0x180046b53  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x180046b58  jmp     loc_180046A0F
0x180046b5d  mov     rcx, r15; pv
0x180046b60  call    cs:__imp_CoTaskMemFree
0x180046b66  jmp     loc_18004685F
```
