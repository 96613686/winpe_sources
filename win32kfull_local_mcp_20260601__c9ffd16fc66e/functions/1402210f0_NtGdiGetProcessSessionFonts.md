# NtGdiGetProcessSessionFonts

- ea: `0x1402210f0`
- end: `0x1402214f7`
- name: `NtGdiGetProcessSessionFonts`
- size: `1031`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1400a4a38`
- `0x140107e00`
- `0x1401633a4`
- `0x1402210f0`
- `0x140221500`

## import_xrefs

- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1402214d8`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1402214d8`
- `ntoskrnl!ExRaiseStatus` at `0x1402211e0`
- `ntoskrnl!ExRaiseStatus` at `0x1402211e0`
- `ntoskrnl!PsProcessType` at `0x140221243`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14022125a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14022125a`
- `ntoskrnl!NtClose` at `0x140221493`
- `ntoskrnl!NtClose` at `0x140221493`
- `ntoskrnl!RtlGetCurrentServiceSessionId` at `0x140221152`
- `ntoskrnl!RtlGetCurrentServiceSessionId` at `0x140221152`
- `ntoskrnl!ObfDereferenceObject` at `0x1402213ba`
- `ntoskrnl!ObfDereferenceObject` at `0x1402213ba`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1402212eb`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140221313`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14022134f`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14022137e`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1402212eb`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140221313`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14022134f`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14022137e`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140221182`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1402211a5`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140221182`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1402211a5`
- `win32kbase!EngSetLastError` at `0x1402214e6`
- `win32kbase!EngSetLastError` at `0x1402214e6`
- `win32kbase!Win32FreePool` at `0x1402214b1`
- `win32kbase!Win32FreePool` at `0x1402214c5`
- `win32kbase!Win32FreePool` at `0x1402214b1`
- `win32kbase!Win32FreePool` at `0x1402214c5`

## pseudocode

```c
__int64 __fastcall NtGdiGetProcessSessionFonts(void *a1, void *a2, void *a3, void *a4, void *a5)
{
  PVOID v6; // r13
  void **v7; // rsi
  unsigned __int16 *v8; // r15
  bool v9; // r12
  int CurrentServiceSessionId; // ebx
  char v11; // al
  int v12; // ebx
  int ProcessSessionFonts; // eax
  __int64 i; // r12
  ULONG v16; // eax
  char v17; // [rsp+40h] [rbp-78h]
  unsigned int v18; // [rsp+44h] [rbp-74h] BYREF
  unsigned int v19; // [rsp+48h] [rbp-70h] BYREF
  unsigned int v20; // [rsp+4Ch] [rbp-6Ch] BYREF
  unsigned int v21; // [rsp+50h] [rbp-68h] BYREF
  PVOID v22; // [rsp+58h] [rbp-60h]
  void **v23; // [rsp+60h] [rbp-58h]
  unsigned __int16 *v24; // [rsp+68h] [rbp-50h]
  PVOID Object; // [rsp+70h] [rbp-48h] BYREF
  unsigned __int64 v26; // [rsp+78h] [rbp-40h]

  v19 = 0;
  v21 = 0;
  v20 = 0;
  v18 = 0;
  v6 = 0;
  v22 = 0;
  v7 = 0;
  v23 = 0;
  v8 = 0;
  v24 = 0;
  v9 = 0;
  CurrentServiceSessionId = RtlGetCurrentServiceSessionId();
  if ( (unsigned int)W32GetCurrentWin32kSessionId() != CurrentServiceSessionId )
    return 0;
  GreProbeAndReadFromUntrustedVa(&v20, 4u, a3, 4u, 4u);
  GreProbeAndReadFromUntrustedVa(&v18, 4u, a5, 4u, 4u);
  Object = (PVOID)(8LL * v20);
  if ( (unsigned __int64)Object > 0xFFFFFFFF || (v26 = 2LL * v18, v26 > 0xFFFFFFFF) )
    ExRaiseStatus(-1073741675);
  if ( v20 )
  {
    v11 = 0;
    v17 = 0;
  }
  else if ( a2 || a4 || (v11 = 1, v17 = 1, v18) )
  {
    v12 = -1073741811;
    goto LABEL_36;
  }
  if ( v11
    || (v7 = (void **)PALLOCMEM(8 * v20, 1886221383), (v23 = v7) != 0)
    && (v8 = (unsigned __int16 *)PALLOCNOZ(2 * v18, 1886221383), (v24 = v8) != 0) )
  {
    Object = 0;
    v12 = ObReferenceObjectByHandle(a1, 0x40u, (POBJECT_TYPE)PsProcessType, 1, &Object, 0);
    v6 = Object;
    v22 = Object;
    if ( v12 >= 0 )
    {
      ProcessSessionFonts = GetProcessSessionFonts((PRKPROCESS)Object, v20, v18, &v19, &v21, v7, v8);
      v12 = ProcessSessionFonts;
      if ( ProcessSessionFonts >= 0 )
        v9 = v17 == 0;
      if ( (int)(ProcessSessionFonts + 0x80000000) < 0 || ProcessSessionFonts == -1073741789 )
      {
        GreProbeAndWriteToUntrustedVa(a3, 4u, &v19, 4u, 4u);
        GreProbeAndWriteToUntrustedVa(a5, 4u, &v21, 4u, 4u);
      }
      if ( v12 >= 0 && !v17 )
      {
        GreProbeAndWriteToUntrustedVa(a2, 8LL * v20, v7, 8LL * v19, 4u);
        GreProbeAndWriteToUntrustedVa(a4, 2LL * v18, v8, 2LL * v21, 4u);
      }
    }
    if ( v12 >= 0 )
      goto LABEL_18;
  }
  else
  {
    v12 = -1073741801;
  }
LABEL_36:
  if ( v9 )
  {
    for ( i = 0; (unsigned int)i < v19; i = (unsigned int)(i + 1) )
      NtClose(v7[i]);
  }
LABEL_18:
  if ( v6 )
    ObfDereferenceObject(v6);
  if ( v7 )
    Win32FreePool(v7);
  if ( v8 )
    Win32FreePool(v8);
  if ( v12 < 0 )
  {
    v16 = RtlNtStatusToDosErrorNoTeb(v12);
    EngSetLastError(v16);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1402210f0  mov     rax, rsp
0x1402210f3  mov     [rax+20h], r9
0x1402210f7  mov     [rax+18h], r8
0x1402210fb  mov     [rax+10h], rdx
0x1402210ff  mov     [rax+8], rcx
0x140221103  push    rbx
0x140221104  push    rsi
0x140221105  push    r12
0x140221107  push    r13
0x140221109  push    r14
0x14022110b  push    r15
0x14022110d  sub     rsp, 88h
0x140221114  mov     r14, r8
0x140221117  mov     dword ptr [rax-70h], 0
0x14022111e  mov     dword ptr [rax-68h], 0
0x140221125  mov     dword ptr [rax-6Ch], 0
0x14022112c  mov     dword ptr [rax-74h], 0
0x140221133  xor     r13d, r13d
0x140221136  mov     [rsp+0B8h+var_60], r13
0x14022113b  xor     esi, esi
0x14022113d  mov     [rsp+0B8h+var_58], rsi
0x140221142  xor     r15d, r15d
0x140221145  mov     [rsp+0B8h+var_50], r15
0x14022114a  xor     r12b, r12b
0x14022114d  mov     [rsp+0B8h+var_77], r12b
0x140221152  call    cs:__imp_RtlGetCurrentServiceSessionId
0x140221159  nop     dword ptr [rax+rax+00h]
0x14022115e  mov     ebx, eax
0x140221160  call    W32GetCurrentWin32kSessionId
0x140221165  cmp     eax, ebx
0x140221167  jnz     loc_140221466
0x14022116d  lea     ebx, [rsi+4]
0x140221170  mov     [rsp+0B8h+Object], rbx
0x140221175  mov     r9d, ebx
0x140221178  mov     r8, r14
0x14022117b  mov     edx, ebx
0x14022117d  lea     rcx, [rsp+0B8h+var_6C]
0x140221182  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x140221189  nop     dword ptr [rax+rax+00h]
0x14022118e  mov     [rsp+0B8h+Object], rbx
0x140221193  mov     r9d, ebx
0x140221196  mov     r8, [rsp+0B8h+arg_20]
0x14022119e  mov     edx, ebx
0x1402211a0  lea     rcx, [rsp+0B8h+var_74]
0x1402211a5  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x1402211ac  nop     dword ptr [rax+rax+00h]
0x1402211b1  mov     ecx, [rsp+0B8h+var_6C]
0x1402211b5  mov     eax, ecx
0x1402211b7  shl     rax, 3
0x1402211bb  mov     [rsp+0B8h+var_48], rax
0x1402211c0  mov     edx, 0FFFFFFFFh
0x1402211c5  cmp     rax, rdx
0x1402211c8  ja      short loc_1402211DB
0x1402211ca  mov     eax, [rsp+0B8h+var_74]
0x1402211ce  add     rax, rax
0x1402211d1  mov     [rsp+0B8h+var_40], rax
0x1402211d6  cmp     rax, rdx
0x1402211d9  jbe     short loc_140221208
0x1402211db  mov     ecx, 0C0000095h; Status
0x1402211e0  call    cs:__imp_ExRaiseStatus
0x1402211ed  mov     ebx, eax
0x1402211ef  mov     r14d, 1
0x1402211f5  mov     r13, [rsp+0B8h+var_60]
0x1402211fa  mov     rsi, r13
0x1402211fd  mov     r15, r13
0x140221200  mov     r12b, sil
0x140221203  jmp     loc_1402213AA
0x140221208  test    ecx, ecx
0x14022120a  jz      loc_1402213F5
0x140221210  xor     al, al
0x140221212  mov     [rsp+0B8h+var_78], al
0x140221216  mov     r14d, 1
0x14022121c  test    al, al
0x14022121e  jz      loc_140221425
0x140221224  mov     [rsp+0B8h+var_48], 0
0x14022122d  mov     [rsp+0B8h+HandleInformation], 0; HandleInformation
0x140221236  lea     rax, [rsp+0B8h+var_48]
0x14022123b  mov     [rsp+0B8h+Object], rax; Object
0x140221240  mov     r9b, r14b; AccessMode
0x140221243  mov     r8, cs:__imp_PsProcessType
0x14022124a  mov     r8, [r8]; ObjectType
0x14022124d  mov     edx, 40h ; '@'; DesiredAccess
0x140221252  mov     rcx, [rsp+0B8h+Handle]; Handle
0x14022125a  call    cs:__imp_ObReferenceObjectByHandle
0x140221261  nop     dword ptr [rax+rax+00h]
0x140221266  mov     ebx, eax
0x140221268  mov     r13, [rsp+0B8h+var_48]
0x14022126d  mov     [rsp+0B8h+var_60], r13
0x140221272  test    eax, eax
0x140221274  js      loc_1402213AA
0x14022127a  mov     [rsp+0B8h+var_88], r15; unsigned __int16 *
0x14022127f  mov     [rsp+0B8h+HandleInformation], rsi; void **
0x140221284  lea     rax, [rsp+0B8h+var_68]
0x140221289  mov     [rsp+0B8h+Object], rax; unsigned int *
0x14022128e  lea     r9, [rsp+0B8h+var_70]; unsigned int *
0x140221293  mov     r8d, [rsp+0B8h+var_74]; unsigned int
0x140221298  mov     edx, [rsp+0B8h+var_6C]; unsigned int
0x14022129c  mov     rcx, r13; PROCESS
0x14022129f  call    ?GetProcessSessionFonts@@YAJPEAU_EPROCESS@@IIPEAI1PEAPEAXPEAG@Z; GetProcessSessionFonts(_EPROCESS *,uint,uint,uint *,uint *,void * *,ushort *)
0x1402212a4  mov     ebx, eax
0x1402212a6  test    eax, eax
0x1402212a8  js      short loc_1402212BC
0x1402212aa  movzx   r12d, r12b
0x1402212ae  cmp     [rsp+0B8h+var_78], 0
0x1402212b3  cmovz   r12d, r14d
0x1402212b7  mov     [rsp+0B8h+var_77], r12b
0x1402212bc  mov     ecx, 80000000h
0x1402212c1  add     eax, ecx
0x1402212c3  test    ecx, eax
0x1402212c5  jnz     short loc_1402212CF
0x1402212c7  cmp     ebx, 0C0000023h
0x1402212cd  jnz     short loc_14022131F
0x1402212cf  mov     eax, 4
0x1402212d4  mov     [rsp+0B8h+Object], rax
0x1402212d9  mov     r9d, eax
0x1402212dc  lea     r8, [rsp+0B8h+var_70]
0x1402212e1  mov     edx, eax
0x1402212e3  mov     rcx, [rsp+0B8h+arg_10]
0x1402212eb  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x1402212f2  nop     dword ptr [rax+rax+00h]
0x1402212f7  mov     eax, 4
0x1402212fc  mov     [rsp+0B8h+Object], rax
0x140221301  mov     r9d, eax
0x140221304  lea     r8, [rsp+0B8h+var_68]
0x140221309  mov     edx, eax
0x14022130b  mov     rcx, [rsp+0B8h+arg_20]
0x140221313  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14022131a  nop     dword ptr [rax+rax+00h]
0x14022131f  test    ebx, ebx
0x140221321  js      short loc_14022138C
0x140221323  cmp     [rsp+0B8h+var_78], 0
0x140221328  jnz     short loc_14022138C
0x14022132a  mov     r9d, [rsp+0B8h+var_70]
0x14022132f  shl     r9, 3
0x140221333  mov     edx, [rsp+0B8h+var_6C]
0x140221337  shl     rdx, 3
0x14022133b  mov     [rsp+0B8h+Object], 4
0x140221344  mov     r8, rsi
0x140221347  mov     rcx, [rsp+0B8h+arg_8]
0x14022134f  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x140221356  nop     dword ptr [rax+rax+00h]
0x14022135b  mov     r9d, [rsp+0B8h+var_68]
0x140221360  add     r9, r9
0x140221363  mov     edx, [rsp+0B8h+var_74]
0x140221367  add     rdx, rdx
0x14022136a  mov     [rsp+0B8h+Object], 4
0x140221373  mov     r8, r15
0x140221376  mov     rcx, [rsp+0B8h+arg_18]
0x14022137e  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x140221385  nop     dword ptr [rax+rax+00h]
0x14022138a  jmp     short loc_1402213AA
0x14022138c  jmp     short loc_1402213AA
0x14022138e  mov     ebx, eax
0x140221390  mov     r14d, 1
0x140221396  mov     r13, [rsp+0B8h+var_60]
0x14022139b  mov     rsi, [rsp+0B8h+var_58]
0x1402213a0  mov     r15, [rsp+0B8h+var_50]
0x1402213a5  mov     r12b, [rsp+0B8h+var_77]
0x1402213aa  test    ebx, ebx
0x1402213ac  js      loc_140221478
0x1402213b2  test    r13, r13
0x1402213b5  jz      short loc_1402213C6
0x1402213b7  mov     rcx, r13; Object
0x1402213ba  call    cs:__imp_ObfDereferenceObject
0x1402213c1  nop     dword ptr [rax+rax+00h]
0x1402213c6  test    rsi, rsi
0x1402213c9  jnz     loc_1402214AE
0x1402213cf  test    r15, r15
0x1402213d2  jnz     loc_1402214C2
0x1402213d8  test    ebx, ebx
0x1402213da  js      loc_1402214D6
0x1402213e0  mov     eax, ebx
0x1402213e2  add     rsp, 88h
0x1402213e9  pop     r15
0x1402213eb  pop     r14
0x1402213ed  pop     r13
0x1402213ef  pop     r12
0x1402213f1  pop     rsi
0x1402213f2  pop     rbx
0x1402213f3  retn
0x1402213f5  cmp     [rsp+0B8h+arg_8], 0
0x1402213fe  jnz     short loc_14022146D
0x140221400  cmp     [rsp+0B8h+arg_18], 0
0x140221409  jnz     short loc_14022146D
0x14022140b  mov     r14d, 1
0x140221411  mov     al, r14b
0x140221414  mov     [rsp+0B8h+var_78], al
0x140221418  cmp     [rsp+0B8h+var_74], 0
0x14022141d  jz      loc_14022121C
0x140221423  jmp     short loc_140221473
0x140221425  shl     ecx, 3
0x140221428  mov     ebx, 706D7447h
0x14022142d  mov     edx, ebx
0x14022142f  call    PALLOCMEM
0x140221434  mov     rsi, rax
0x140221437  mov     [rsp+0B8h+var_58], rax
0x14022143c  test    rax, rax
0x14022143f  jz      short loc_14022145F
0x140221441  mov     ecx, [rsp+0B8h+var_74]
0x140221445  add     ecx, ecx
0x140221447  mov     edx, ebx
0x140221449  call    PALLOCNOZ
0x14022144e  mov     r15, rax
0x140221451  mov     [rsp+0B8h+var_50], rax
0x140221456  test    rax, rax
0x140221459  jnz     loc_140221224
0x14022145f  mov     ebx, 0C0000017h
0x140221464  jmp     short loc_140221478
0x140221466  xor     eax, eax
0x140221468  jmp     loc_1402213E2
0x14022146d  mov     r14d, 1
0x140221473  mov     ebx, 0C000000Dh
0x140221478  test    r12b, r12b
0x14022147b  jz      loc_1402213B2
0x140221481  xor     r12d, r12d
0x140221484  cmp     [rsp+0B8h+var_70], r12d
0x140221489  jbe     loc_1402213B2
0x14022148f  mov     rcx, [rsi+r12*8]; Handle
0x140221493  call    cs:__imp_NtClose
0x14022149a  nop     dword ptr [rax+rax+00h]
0x14022149f  add     r12d, r14d
0x1402214a2  cmp     r12d, [rsp+0B8h+var_70]
0x1402214a7  jb      short loc_14022148F
0x1402214a9  jmp     loc_1402213B2
0x1402214ae  mov     rcx, rsi
0x1402214b1  call    cs:__imp_Win32FreePool
0x1402214b8  nop     dword ptr [rax+rax+00h]
0x1402214bd  jmp     loc_1402213CF
0x1402214c2  mov     rcx, r15
0x1402214c5  call    cs:__imp_Win32FreePool
0x1402214cc  nop     dword ptr [rax+rax+00h]
0x1402214d1  jmp     loc_1402213D8
0x1402214d6  mov     ecx, ebx; Status
0x1402214d8  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1402214df  nop     dword ptr [rax+rax+00h]
0x1402214e4  mov     ecx, eax; iError
0x1402214e6  call    cs:__imp_EngSetLastError
0x1402214ed  nop     dword ptr [rax+rax+00h]
0x1402214f2  jmp     loc_1402213E0
```
