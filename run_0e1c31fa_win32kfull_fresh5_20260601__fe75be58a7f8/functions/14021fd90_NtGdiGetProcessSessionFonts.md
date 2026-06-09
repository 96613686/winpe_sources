# NtGdiGetProcessSessionFonts

- ea: `0x14021fd90`
- end: `0x140220197`
- name: `NtGdiGetProcessSessionFonts`
- size: `1031`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x140053654`
- `0x140077cc8`
- `0x14013db54`
- `0x14021fd90`
- `0x1402201a0`

## import_xrefs

- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x140220178`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x140220178`
- `ntoskrnl!ExRaiseStatus` at `0x14021fe80`
- `ntoskrnl!ExRaiseStatus` at `0x14021fe80`
- `ntoskrnl!PsProcessType` at `0x14021fee3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14021fefa`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14021fefa`
- `ntoskrnl!NtClose` at `0x140220133`
- `ntoskrnl!NtClose` at `0x140220133`
- `ntoskrnl!RtlGetCurrentServiceSessionId` at `0x14021fdf2`
- `ntoskrnl!RtlGetCurrentServiceSessionId` at `0x14021fdf2`
- `ntoskrnl!ObfDereferenceObject` at `0x14022005a`
- `ntoskrnl!ObfDereferenceObject` at `0x14022005a`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14021ff8b`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14021ffb3`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14021ffef`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14022001e`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14021ff8b`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14021ffb3`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14021ffef`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14022001e`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14021fe22`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14021fe45`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14021fe22`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14021fe45`
- `win32kbase!EngSetLastError` at `0x140220186`
- `win32kbase!EngSetLastError` at `0x140220186`
- `win32kbase!Win32FreePool` at `0x140220151`
- `win32kbase!Win32FreePool` at `0x140220165`
- `win32kbase!Win32FreePool` at `0x140220151`
- `win32kbase!Win32FreePool` at `0x140220165`

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
0x14021fd90  mov     rax, rsp
0x14021fd93  mov     [rax+20h], r9
0x14021fd97  mov     [rax+18h], r8
0x14021fd9b  mov     [rax+10h], rdx
0x14021fd9f  mov     [rax+8], rcx
0x14021fda3  push    rbx
0x14021fda4  push    rsi
0x14021fda5  push    r12
0x14021fda7  push    r13
0x14021fda9  push    r14
0x14021fdab  push    r15
0x14021fdad  sub     rsp, 88h
0x14021fdb4  mov     r14, r8
0x14021fdb7  mov     dword ptr [rax-70h], 0
0x14021fdbe  mov     dword ptr [rax-68h], 0
0x14021fdc5  mov     dword ptr [rax-6Ch], 0
0x14021fdcc  mov     dword ptr [rax-74h], 0
0x14021fdd3  xor     r13d, r13d
0x14021fdd6  mov     [rsp+0B8h+var_60], r13
0x14021fddb  xor     esi, esi
0x14021fddd  mov     [rsp+0B8h+var_58], rsi
0x14021fde2  xor     r15d, r15d
0x14021fde5  mov     [rsp+0B8h+var_50], r15
0x14021fdea  xor     r12b, r12b
0x14021fded  mov     [rsp+0B8h+var_77], r12b
0x14021fdf2  call    cs:__imp_RtlGetCurrentServiceSessionId
0x14021fdf9  nop     dword ptr [rax+rax+00h]
0x14021fdfe  mov     ebx, eax
0x14021fe00  call    W32GetCurrentWin32kSessionId
0x14021fe05  cmp     eax, ebx
0x14021fe07  jnz     loc_140220106
0x14021fe0d  lea     ebx, [rsi+4]
0x14021fe10  mov     [rsp+0B8h+Object], rbx
0x14021fe15  mov     r9d, ebx
0x14021fe18  mov     r8, r14
0x14021fe1b  mov     edx, ebx
0x14021fe1d  lea     rcx, [rsp+0B8h+var_6C]
0x14021fe22  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14021fe29  nop     dword ptr [rax+rax+00h]
0x14021fe2e  mov     [rsp+0B8h+Object], rbx
0x14021fe33  mov     r9d, ebx
0x14021fe36  mov     r8, [rsp+0B8h+arg_20]
0x14021fe3e  mov     edx, ebx
0x14021fe40  lea     rcx, [rsp+0B8h+var_74]
0x14021fe45  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14021fe4c  nop     dword ptr [rax+rax+00h]
0x14021fe51  mov     ecx, [rsp+0B8h+var_6C]
0x14021fe55  mov     eax, ecx
0x14021fe57  shl     rax, 3
0x14021fe5b  mov     [rsp+0B8h+var_48], rax
0x14021fe60  mov     edx, 0FFFFFFFFh
0x14021fe65  cmp     rax, rdx
0x14021fe68  ja      short loc_14021FE7B
0x14021fe6a  mov     eax, [rsp+0B8h+var_74]
0x14021fe6e  add     rax, rax
0x14021fe71  mov     [rsp+0B8h+var_40], rax
0x14021fe76  cmp     rax, rdx
0x14021fe79  jbe     short loc_14021FEA8
0x14021fe7b  mov     ecx, 0C0000095h; Status
0x14021fe80  call    cs:__imp_ExRaiseStatus
0x14021fe8d  mov     ebx, eax
0x14021fe8f  mov     r14d, 1
0x14021fe95  mov     r13, [rsp+0B8h+var_60]
0x14021fe9a  mov     rsi, r13
0x14021fe9d  mov     r15, r13
0x14021fea0  mov     r12b, sil
0x14021fea3  jmp     loc_14022004A
0x14021fea8  test    ecx, ecx
0x14021feaa  jz      loc_140220095
0x14021feb0  xor     al, al
0x14021feb2  mov     [rsp+0B8h+var_78], al
0x14021feb6  mov     r14d, 1
0x14021febc  test    al, al
0x14021febe  jz      loc_1402200C5
0x14021fec4  mov     [rsp+0B8h+var_48], 0
0x14021fecd  mov     [rsp+0B8h+HandleInformation], 0; HandleInformation
0x14021fed6  lea     rax, [rsp+0B8h+var_48]
0x14021fedb  mov     [rsp+0B8h+Object], rax; Object
0x14021fee0  mov     r9b, r14b; AccessMode
0x14021fee3  mov     r8, cs:__imp_PsProcessType
0x14021feea  mov     r8, [r8]; ObjectType
0x14021feed  mov     edx, 40h ; '@'; DesiredAccess
0x14021fef2  mov     rcx, [rsp+0B8h+Handle]; Handle
0x14021fefa  call    cs:__imp_ObReferenceObjectByHandle
0x14021ff01  nop     dword ptr [rax+rax+00h]
0x14021ff06  mov     ebx, eax
0x14021ff08  mov     r13, [rsp+0B8h+var_48]
0x14021ff0d  mov     [rsp+0B8h+var_60], r13
0x14021ff12  test    eax, eax
0x14021ff14  js      loc_14022004A
0x14021ff1a  mov     [rsp+0B8h+var_88], r15; unsigned __int16 *
0x14021ff1f  mov     [rsp+0B8h+HandleInformation], rsi; void **
0x14021ff24  lea     rax, [rsp+0B8h+var_68]
0x14021ff29  mov     [rsp+0B8h+Object], rax; unsigned int *
0x14021ff2e  lea     r9, [rsp+0B8h+var_70]; unsigned int *
0x14021ff33  mov     r8d, [rsp+0B8h+var_74]; unsigned int
0x14021ff38  mov     edx, [rsp+0B8h+var_6C]; unsigned int
0x14021ff3c  mov     rcx, r13; PROCESS
0x14021ff3f  call    ?GetProcessSessionFonts@@YAJPEAU_EPROCESS@@IIPEAI1PEAPEAXPEAG@Z; GetProcessSessionFonts(_EPROCESS *,uint,uint,uint *,uint *,void * *,ushort *)
0x14021ff44  mov     ebx, eax
0x14021ff46  test    eax, eax
0x14021ff48  js      short loc_14021FF5C
0x14021ff4a  movzx   r12d, r12b
0x14021ff4e  cmp     [rsp+0B8h+var_78], 0
0x14021ff53  cmovz   r12d, r14d
0x14021ff57  mov     [rsp+0B8h+var_77], r12b
0x14021ff5c  mov     ecx, 80000000h
0x14021ff61  add     eax, ecx
0x14021ff63  test    ecx, eax
0x14021ff65  jnz     short loc_14021FF6F
0x14021ff67  cmp     ebx, 0C0000023h
0x14021ff6d  jnz     short loc_14021FFBF
0x14021ff6f  mov     eax, 4
0x14021ff74  mov     [rsp+0B8h+Object], rax
0x14021ff79  mov     r9d, eax
0x14021ff7c  lea     r8, [rsp+0B8h+var_70]
0x14021ff81  mov     edx, eax
0x14021ff83  mov     rcx, [rsp+0B8h+arg_10]
0x14021ff8b  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14021ff92  nop     dword ptr [rax+rax+00h]
0x14021ff97  mov     eax, 4
0x14021ff9c  mov     [rsp+0B8h+Object], rax
0x14021ffa1  mov     r9d, eax
0x14021ffa4  lea     r8, [rsp+0B8h+var_68]
0x14021ffa9  mov     edx, eax
0x14021ffab  mov     rcx, [rsp+0B8h+arg_20]
0x14021ffb3  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14021ffba  nop     dword ptr [rax+rax+00h]
0x14021ffbf  test    ebx, ebx
0x14021ffc1  js      short loc_14022002C
0x14021ffc3  cmp     [rsp+0B8h+var_78], 0
0x14021ffc8  jnz     short loc_14022002C
0x14021ffca  mov     r9d, [rsp+0B8h+var_70]
0x14021ffcf  shl     r9, 3
0x14021ffd3  mov     edx, [rsp+0B8h+var_6C]
0x14021ffd7  shl     rdx, 3
0x14021ffdb  mov     [rsp+0B8h+Object], 4
0x14021ffe4  mov     r8, rsi
0x14021ffe7  mov     rcx, [rsp+0B8h+arg_8]
0x14021ffef  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14021fff6  nop     dword ptr [rax+rax+00h]
0x14021fffb  mov     r9d, [rsp+0B8h+var_68]
0x140220000  add     r9, r9
0x140220003  mov     edx, [rsp+0B8h+var_74]
0x140220007  add     rdx, rdx
0x14022000a  mov     [rsp+0B8h+Object], 4
0x140220013  mov     r8, r15
0x140220016  mov     rcx, [rsp+0B8h+arg_18]
0x14022001e  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x140220025  nop     dword ptr [rax+rax+00h]
0x14022002a  jmp     short loc_14022004A
0x14022002c  jmp     short loc_14022004A
0x14022002e  mov     ebx, eax
0x140220030  mov     r14d, 1
0x140220036  mov     r13, [rsp+0B8h+var_60]
0x14022003b  mov     rsi, [rsp+0B8h+var_58]
0x140220040  mov     r15, [rsp+0B8h+var_50]
0x140220045  mov     r12b, [rsp+0B8h+var_77]
0x14022004a  test    ebx, ebx
0x14022004c  js      loc_140220118
0x140220052  test    r13, r13
0x140220055  jz      short loc_140220066
0x140220057  mov     rcx, r13; Object
0x14022005a  call    cs:__imp_ObfDereferenceObject
0x140220061  nop     dword ptr [rax+rax+00h]
0x140220066  test    rsi, rsi
0x140220069  jnz     loc_14022014E
0x14022006f  test    r15, r15
0x140220072  jnz     loc_140220162
0x140220078  test    ebx, ebx
0x14022007a  js      loc_140220176
0x140220080  mov     eax, ebx
0x140220082  add     rsp, 88h
0x140220089  pop     r15
0x14022008b  pop     r14
0x14022008d  pop     r13
0x14022008f  pop     r12
0x140220091  pop     rsi
0x140220092  pop     rbx
0x140220093  retn
0x140220095  cmp     [rsp+0B8h+arg_8], 0
0x14022009e  jnz     short loc_14022010D
0x1402200a0  cmp     [rsp+0B8h+arg_18], 0
0x1402200a9  jnz     short loc_14022010D
0x1402200ab  mov     r14d, 1
0x1402200b1  mov     al, r14b
0x1402200b4  mov     [rsp+0B8h+var_78], al
0x1402200b8  cmp     [rsp+0B8h+var_74], 0
0x1402200bd  jz      loc_14021FEBC
0x1402200c3  jmp     short loc_140220113
0x1402200c5  shl     ecx, 3
0x1402200c8  mov     ebx, 706D7447h
0x1402200cd  mov     edx, ebx
0x1402200cf  call    PALLOCMEM
0x1402200d4  mov     rsi, rax
0x1402200d7  mov     [rsp+0B8h+var_58], rax
0x1402200dc  test    rax, rax
0x1402200df  jz      short loc_1402200FF
0x1402200e1  mov     ecx, [rsp+0B8h+var_74]
0x1402200e5  add     ecx, ecx
0x1402200e7  mov     edx, ebx
0x1402200e9  call    PALLOCNOZ
0x1402200ee  mov     r15, rax
0x1402200f1  mov     [rsp+0B8h+var_50], rax
0x1402200f6  test    rax, rax
0x1402200f9  jnz     loc_14021FEC4
0x1402200ff  mov     ebx, 0C0000017h
0x140220104  jmp     short loc_140220118
0x140220106  xor     eax, eax
0x140220108  jmp     loc_140220082
0x14022010d  mov     r14d, 1
0x140220113  mov     ebx, 0C000000Dh
0x140220118  test    r12b, r12b
0x14022011b  jz      loc_140220052
0x140220121  xor     r12d, r12d
0x140220124  cmp     [rsp+0B8h+var_70], r12d
0x140220129  jbe     loc_140220052
0x14022012f  mov     rcx, [rsi+r12*8]; Handle
0x140220133  call    cs:__imp_NtClose
0x14022013a  nop     dword ptr [rax+rax+00h]
0x14022013f  add     r12d, r14d
0x140220142  cmp     r12d, [rsp+0B8h+var_70]
0x140220147  jb      short loc_14022012F
0x140220149  jmp     loc_140220052
0x14022014e  mov     rcx, rsi
0x140220151  call    cs:__imp_Win32FreePool
0x140220158  nop     dword ptr [rax+rax+00h]
0x14022015d  jmp     loc_14022006F
0x140220162  mov     rcx, r15
0x140220165  call    cs:__imp_Win32FreePool
0x14022016c  nop     dword ptr [rax+rax+00h]
0x140220171  jmp     loc_140220078
0x140220176  mov     ecx, ebx; Status
0x140220178  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14022017f  nop     dword ptr [rax+rax+00h]
0x140220184  mov     ecx, eax; iError
0x140220186  call    cs:__imp_EngSetLastError
0x14022018d  nop     dword ptr [rax+rax+00h]
0x140220192  jmp     loc_140220080
```
