# RtmRegisterForChangeNotification

- ea: `0x180003fb0`
- end: `0x180004210`
- name: `RtmRegisterForChangeNotification`
- size: `608`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_VIEW_SET TargetViews, RTM_NOTIFY_FLAGS NotifyFlags, PVOID NotifyContext, PRTM_NOTIFY_HANDLE NotifyHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180013b00`

## callees

- `0x180003fb0`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800040d8`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800040d8`
- `ntdll!RtlReleaseResource` at `0x180004186`
- `ntdll!RtlReleaseResource` at `0x180004186`
- `KERNEL32!HeapAlloc` at `0x18000404e`
- `KERNEL32!HeapAlloc` at `0x18000404e`
- `KERNEL32!GetProcessHeap` at `0x18000403d`
- `KERNEL32!GetProcessHeap` at `0x1800041c9`
- `KERNEL32!GetProcessHeap` at `0x18000403d`
- `KERNEL32!GetProcessHeap` at `0x1800041c9`
- `KERNEL32!HeapFree` at `0x1800041d7`
- `KERNEL32!HeapFree` at `0x1800041d7`
- `KERNEL32!InitializeCriticalSection` at `0x18000409a`
- `KERNEL32!InitializeCriticalSection` at `0x18000409a`
- `KERNEL32!DeleteCriticalSection` at `0x1800041c3`
- `KERNEL32!DeleteCriticalSection` at `0x1800041c3`

## pseudocode

```c
DWORD __stdcall RtmRegisterForChangeNotification(
        RTM_ENTITY_HANDLE RtmRegHandle,
        RTM_VIEW_SET TargetViews,
        RTM_NOTIFY_FLAGS NotifyFlags,
        PVOID NotifyContext,
        PRTM_NOTIFY_HANDLE NotifyHandle)
{
  volatile signed __int32 *v6; // r15
  __int64 v8; // r14
  unsigned __int64 v9; // rax
  RTM_VIEW_SET v10; // r12d
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  char *v13; // rax
  unsigned __int64 v14; // rbx
  RTM_VIEW_SET v15; // ecx
  int i; // edx
  unsigned int v17; // edx
  DWORD v18; // r14d
  __int64 j; // rcx
  int v20; // r8d
  RTM_NOTIFY_FLAGS v21; // edx
  __int64 v22; // rcx
  __int64 k; // rax
  HANDLE v24; // rax
  struct _RTL_RESOURCE *Resource; // [rsp+60h] [rbp+8h]

  v6 = (volatile signed __int32 *)((unsigned __int64)RtmRegHandle ^ 0x7754DF32);
  if ( (unsigned __int64)RtmRegHandle == 0x7754DF32
    || *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) == 1 )
  {
    return 6;
  }
  if ( (NotifyFlags & 7) == 0 )
    return 87;
  v8 = *(_QWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x10);
  if ( (~*(_DWORD *)(v8 + 40) & TargetViews) != 0 )
    return 50;
  v9 = 8LL * *(unsigned int *)(v8 + 304);
  v10 = -1;
  if ( v9 > 0xFFFFFFFF || (int)v9 + 104 < (unsigned int)v9 )
    return 534;
  v11 = v9 + 104;
  ProcessHeap = GetProcessHeap();
  v13 = (char *)HeapAlloc(ProcessHeap, 8u, v11);
  v14 = (unsigned __int64)v13;
  if ( !v13 )
    return 8;
  *((_QWORD *)v13 + 1) = v6;
  *((_DWORD *)v13 + 4) = TargetViews;
  v15 = TargetViews;
  for ( i = 0; v15; v15 &= v15 - 1 )
    ++i;
  *((_DWORD *)v13 + 5) = i;
  *((_DWORD *)v13 + 6) = NotifyFlags;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v13 + 32));
  *(_QWORD *)(v14 + 72) = NotifyContext;
  *(_QWORD *)(v14 + 80) = 0;
  *(_DWORD *)(v14 + 88) = *(_DWORD *)(v8 + 304);
  *(_DWORD *)(v14 + 28) = -1;
  Resource = (struct _RTL_RESOURCE *)(v8 + 744);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)(v8 + 744), 1u);
  v17 = *(_DWORD *)(v8 + 844);
  if ( *(_DWORD *)(v8 + 848) < v17 )
  {
    for ( j = 0; (unsigned int)j < v17; j = (unsigned int)(j + 1) )
    {
      if ( !*(_QWORD *)(*(_QWORD *)(v8 + 856) + 8 * j) )
        break;
    }
    *(_DWORD *)(v14 + 28) = j;
    *(_QWORD *)(*(_QWORD *)(v8 + 856) + 8 * j) = v14;
    ++*(_DWORD *)(v8 + 848);
    v20 = 1 << j;
    *(_DWORD *)(v8 + 864) |= 1 << j;
    v21 = NotifyFlags;
    if ( (NotifyFlags & 0x10000) != 0 )
      *(_DWORD *)(v8 + 868) |= v20;
    v22 = 0;
    if ( TargetViews )
      v10 = TargetViews;
    do
    {
      if ( (v10 & 1) != 0 )
        *(_DWORD *)(v8 + 4 * v22 + 872) |= v20;
      v22 = (unsigned int)(v22 + 1);
      v10 >>= 1;
    }
    while ( v10 );
    for ( k = 0; k != 3; ++k )
    {
      if ( (v21 & 1) != 0 )
        *(_DWORD *)(v8 + 4 * k + 1000) |= v20;
      v21 >>= 1;
    }
    v18 = 31;
  }
  else
  {
    v18 = 1450;
  }
  RtlReleaseResource(Resource);
  if ( *(_DWORD *)(v14 + 28) == -1 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(v14 + 32));
    v24 = GetProcessHeap();
    HeapFree(v24, 0, (LPVOID)v14);
    *NotifyHandle = 0;
    return v18;
  }
  else
  {
    _InterlockedAdd(v6, 1u);
    *NotifyHandle = (HANDLE)(v14 ^ 0x7754DF32);
    return 0;
  }
}

```

## disassembly

```asm
0x180003fb0  mov     [rsp+arg_8], rbx
0x180003fb5  mov     [rsp+arg_18], r9
0x180003fba  mov     [rsp+arg_10], r8d
0x180003fbf  push    rsi
0x180003fc0  push    r12
0x180003fc2  push    r13
0x180003fc4  push    r14
0x180003fc6  push    r15
0x180003fc8  sub     rsp, 30h
0x180003fcc  mov     eax, r8d
0x180003fcf  mov     r13d, edx
0x180003fd2  mov     r15, rcx
0x180003fd5  xor     r15, 7754DF32h
0x180003fdc  jz      loc_1800041F8
0x180003fe2  mov     esi, 1
0x180003fe7  cmp     [r15+30h], esi
0x180003feb  jz      loc_1800041F8
0x180003ff1  test    al, 7
0x180003ff3  jnz     short loc_180003FFD
0x180003ff5  lea     eax, [rsi+56h]
0x180003ff8  jmp     loc_1800041FD
0x180003ffd  mov     r14, [r15+10h]
0x180004001  mov     eax, [r14+28h]
0x180004005  not     eax
0x180004007  test    r13d, eax
0x18000400a  jz      short loc_180004016
0x18000400c  mov     eax, 32h ; '2'
0x180004011  jmp     loc_1800041FD
0x180004016  mov     eax, [r14+130h]
0x18000401d  shl     rax, 3
0x180004021  mov     r12d, 0FFFFFFFFh
0x180004027  cmp     rax, r12
0x18000402a  ja      loc_1800041F1
0x180004030  lea     ecx, [rax+68h]
0x180004033  cmp     ecx, eax
0x180004035  jb      loc_1800041F1
0x18000403b  mov     ebx, ecx
0x18000403d  call    cs:__imp_GetProcessHeap
0x180004043  mov     rcx, rax; hHeap
0x180004046  mov     r8d, ebx; dwBytes
0x180004049  mov     edx, 8; dwFlags
0x18000404e  call    cs:__imp_HeapAlloc
0x180004054  mov     rbx, rax
0x180004057  mov     [rsp+58h+Resource], rax
0x18000405c  test    rax, rax
0x18000405f  jnz     short loc_180004069
0x180004061  lea     eax, [rbx+8]
0x180004064  jmp     loc_1800041FD
0x180004069  mov     [rax+8], r15
0x18000406d  mov     [rax+10h], r13d
0x180004071  mov     ecx, r13d
0x180004074  xor     edx, edx
0x180004076  test    r13d, r13d
0x180004079  jz      short loc_180004084
0x18000407b  lea     eax, [rcx-1]
0x18000407e  add     edx, esi
0x180004080  and     ecx, eax
0x180004082  jnz     short loc_18000407B
0x180004084  mov     [rbx+14h], edx
0x180004087  mov     eax, [rsp+58h+arg_10]
0x18000408b  mov     [rbx+18h], eax
0x18000408e  mov     [rsp+58h+var_38], 0
0x180004096  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000409a  call    cs:__imp_InitializeCriticalSection
0x1800040a0  mov     [rsp+58h+var_38], esi
0x1800040a4  mov     rax, [rsp+58h+arg_18]
0x1800040a9  mov     [rbx+48h], rax
0x1800040ad  mov     qword ptr [rbx+50h], 0
0x1800040b5  mov     eax, [r14+130h]
0x1800040bc  mov     [rbx+58h], eax
0x1800040bf  mov     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x1800040c6  lea     rax, [r14+2E8h]
0x1800040cd  mov     [rsp+58h+Resource], rax
0x1800040d2  mov     dl, sil; Wait
0x1800040d5  mov     rcx, rax; Resource
0x1800040d8  call    cs:__imp_RtlAcquireResourceExclusive
0x1800040de  mov     edx, [r14+34Ch]
0x1800040e5  cmp     [r14+350h], edx
0x1800040ec  jb      short loc_1800040F9
0x1800040ee  mov     r14d, 5AAh
0x1800040f4  jmp     loc_180004181
0x1800040f9  xor     ecx, ecx
0x1800040fb  test    edx, edx
0x1800040fd  jz      short loc_180004113
0x1800040ff  mov     r8, [r14+358h]
0x180004106  cmp     qword ptr [r8+rcx*8], 0
0x18000410b  jz      short loc_180004113
0x18000410d  add     ecx, esi
0x18000410f  cmp     ecx, edx
0x180004111  jb      short loc_180004106
0x180004113  mov     [rbx+1Ch], ecx
0x180004116  mov     rax, [r14+358h]
0x18000411d  mov     [rax+rcx*8], rbx
0x180004121  add     [r14+350h], esi
0x180004128  mov     r8d, esi
0x18000412b  shl     r8d, cl
0x18000412e  or      [r14+360h], r8d
0x180004135  mov     edx, [rsp+58h+arg_10]
0x180004139  bt      edx, 10h
0x18000413d  jnb     short loc_180004146
0x18000413f  or      [r14+364h], r8d
0x180004146  xor     ecx, ecx
0x180004148  test    r13d, r13d
0x18000414b  cmovnz  r12d, r13d
0x18000414f  test    sil, r12b
0x180004152  jz      short loc_18000415C
0x180004154  or      [r14+rcx*4+368h], r8d
0x18000415c  add     ecx, esi
0x18000415e  shr     r12d, 1
0x180004161  jnz     short loc_18000414F
0x180004163  xor     eax, eax
0x180004165  test    sil, dl
0x180004168  jz      short loc_180004172
0x18000416a  or      [r14+rax*4+3E8h], r8d
0x180004172  shr     edx, 1
0x180004174  add     rax, rsi
0x180004177  cmp     rax, 3
0x18000417b  jnz     short loc_180004165
0x18000417d  lea     r14d, [rax+1Ch]
0x180004181  mov     rcx, [rsp+58h+Resource]; Resource
0x180004186  call    cs:__imp_RtlReleaseResource
0x18000418c  cmp     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x180004190  jz      short loc_1800041BB
0x180004192  lock add [r15], esi
0x180004196  xor     rbx, 7754DF32h
0x18000419d  mov     rax, [rsp+58h+NotifyHandle]
0x1800041a5  mov     [rax], rbx
0x1800041a8  xor     eax, eax
0x1800041aa  jmp     short loc_1800041FD
0x1800041ac  mov     r14d, 8
0x1800041b2  mov     rbx, [rsp+58h+Resource]
0x1800041b7  mov     esi, [rsp+58h+var_38]
0x1800041bb  test    esi, esi
0x1800041bd  jz      short loc_1800041C9
0x1800041bf  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800041c3  call    cs:__imp_DeleteCriticalSection
0x1800041c9  call    cs:__imp_GetProcessHeap
0x1800041cf  mov     rcx, rax; hHeap
0x1800041d2  mov     r8, rbx; lpMem
0x1800041d5  xor     edx, edx; dwFlags
0x1800041d7  call    cs:__imp_HeapFree
0x1800041dd  mov     rcx, [rsp+58h+NotifyHandle]
0x1800041e5  mov     qword ptr [rcx], 0
0x1800041ec  mov     eax, r14d
0x1800041ef  jmp     short loc_1800041FD
0x1800041f1  mov     eax, 216h
0x1800041f6  jmp     short loc_1800041FD
0x1800041f8  mov     eax, 6
0x1800041fd  mov     rbx, [rsp+58h+arg_8]
0x180004202  add     rsp, 30h
0x180004206  pop     r15
0x180004208  pop     r14
0x18000420a  pop     r13
0x18000420c  pop     r12
0x18000420e  pop     rsi
0x18000420f  retn
```
