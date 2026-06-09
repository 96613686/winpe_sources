# NotificationServiceImpl::AddOutstandingRequest(_LIST_ENTRY *,unsigned __int64,ulong,long,_RequestTypes)

- ea: `0x18006b000`
- end: `0x18006b19b`
- name: `?AddOutstandingRequest@NotificationServiceImpl@@AEAAJPEAU_LIST_ENTRY@@_KKJW4_RequestTypes@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, int, int)`
- caller_count: `9`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18006b5c0`
- `0x18006b930`
- `0x18006be50`
- `0x180072bc0`
- `0x180072f00`
- `0x180073680`
- `0x180073940`
- `0x180073f20`
- `0x1800744d0`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x18006b000`
- `0x180076790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b14d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b14d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b123`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b123`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b076`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b076`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b064`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b064`

## string_xrefs

- `0x18006b0c9`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::AddOutstandingRequest(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        int a6)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rdi
  unsigned int v13; // ebx
  PVOID *v14; // rcx
  _QWORD *v15; // rax
  int v17; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v17 = a4;
    WPP_SF_Iddd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a3);
  }
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, 0x28u);
  v12 = v11;
  if ( v11 )
  {
    *((_DWORD *)v11 + 7) = a4;
    *((_DWORD *)v11 + 6) = a5;
    v11[2] = a3;
    *((_DWORD *)v11 + 8) = a6;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    v15 = *(_QWORD **)(a2 + 8);
    if ( *v15 != a2 )
      __fastfail(3u);
    *v12 = a2;
    v12[1] = v15;
    v13 = 0;
    *v15 = v12;
    *(_QWORD *)(a2 + 8) = v12;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    goto LABEL_16;
  }
  v13 = -2147024882;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, 2147942414LL);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x8BA,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
    (const char *)0x8007000ELL,
    v17);
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
    {
LABEL_17:
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 && *((_BYTE *)v14 + 25) >= 6u )
        WPP_SF_d(v14[2], 222, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v13);
      return v13;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, 2147942414LL);
LABEL_16:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_17;
  }
  return v13;
}

```

## disassembly

```asm
0x18006b000  push    rbx
0x18006b002  push    rbp
0x18006b003  push    rsi
0x18006b004  push    rdi
0x18006b005  push    r13
0x18006b007  push    r14
0x18006b009  push    r15
0x18006b00b  sub     rsp, 40h
0x18006b00f  mov     ebx, r9d
0x18006b012  mov     rbp, r8
0x18006b015  mov     rsi, rdx
0x18006b018  mov     r13, rcx
0x18006b01b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b022  lea     rax, WPP_GLOBAL_Control
0x18006b029  mov     r14d, [rsp+78h+arg_28]
0x18006b031  mov     r15d, [rsp+78h+arg_20]
0x18006b039  cmp     rcx, rax
0x18006b03c  jz      short loc_18006B064
0x18006b03e  test    byte ptr [rcx+1Ch], 2
0x18006b042  jz      short loc_18006B064
0x18006b044  cmp     byte ptr [rcx+19h], 6
0x18006b048  jb      short loc_18006B064
0x18006b04a  mov     rcx, [rcx+10h]
0x18006b04e  mov     r9, r8
0x18006b051  mov     [rsp+78h+var_48], r14d
0x18006b056  mov     [rsp+78h+var_50], r15d
0x18006b05b  mov     [rsp+78h+var_58], ebx; int
0x18006b05f  call    WPP_SF_Iddd
0x18006b064  call    cs:__imp_GetProcessHeap
0x18006b06a  mov     edx, 8; dwFlags
0x18006b06f  mov     rcx, rax; hHeap
0x18006b072  lea     r8d, [rdx+20h]; dwBytes
0x18006b076  call    cs:__imp_HeapAlloc
0x18006b07c  mov     rdi, rax
0x18006b07f  test    rax, rax
0x18006b082  jnz     loc_18006B110
0x18006b088  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b08f  lea     rdi, WPP_GLOBAL_Control
0x18006b096  mov     ebx, 8007000Eh
0x18006b09b  cmp     rcx, rdi
0x18006b09e  jz      short loc_18006B0C4
0x18006b0a0  test    byte ptr [rcx+1Ch], 2
0x18006b0a4  jz      short loc_18006B0C4
0x18006b0a6  cmp     byte ptr [rcx+19h], 2
0x18006b0aa  jb      short loc_18006B0C4
0x18006b0ac  mov     rcx, [rcx+10h]
0x18006b0b0  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006b0b7  mov     edx, 0DCh
0x18006b0bc  mov     r9d, ebx
0x18006b0bf  call    WPP_SF_d
0x18006b0c4  mov     rcx, [rsp+78h]; this
0x18006b0c9  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006b0d0  mov     r9d, ebx; char *
0x18006b0d3  mov     edx, 8BAh; void *
0x18006b0d8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006b0dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b0e4  cmp     rcx, rdi
0x18006b0e7  jz      loc_18006B18A
0x18006b0ed  test    byte ptr [rcx+1Ch], 80h
0x18006b0f1  jz      short loc_18006B161
0x18006b0f3  mov     rcx, [rcx+10h]
0x18006b0f7  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006b0fe  mov     edx, 0DDh
0x18006b103  mov     r9d, 8007000Eh
0x18006b109  call    WPP_SF_d
0x18006b10e  jmp     short loc_18006B15A
0x18006b110  lea     rcx, [r13+10h]; lpCriticalSection
0x18006b114  mov     [rax+1Ch], ebx
0x18006b117  mov     [rax+18h], r15d
0x18006b11b  mov     [rax+10h], rbp
0x18006b11f  mov     [rax+20h], r14d
0x18006b123  call    cs:__imp_EnterCriticalSection
0x18006b129  mov     rax, [rsi+8]
0x18006b12d  cmp     [rax], rsi
0x18006b130  jz      short loc_18006B139
0x18006b132  mov     ecx, 3
0x18006b137  int     29h; Win8: RtlFailFast(ecx)
0x18006b139  mov     [rdi], rsi
0x18006b13c  lea     rcx, [r13+10h]; lpCriticalSection
0x18006b140  mov     [rdi+8], rax
0x18006b144  xor     ebx, ebx
0x18006b146  mov     [rax], rdi
0x18006b149  mov     [rsi+8], rdi
0x18006b14d  call    cs:__imp_LeaveCriticalSection
0x18006b153  lea     rdi, WPP_GLOBAL_Control
0x18006b15a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b161  cmp     rcx, rdi
0x18006b164  jz      short loc_18006B18A
0x18006b166  test    byte ptr [rcx+1Ch], 2
0x18006b16a  jz      short loc_18006B18A
0x18006b16c  cmp     byte ptr [rcx+19h], 6
0x18006b170  jb      short loc_18006B18A
0x18006b172  mov     rcx, [rcx+10h]
0x18006b176  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006b17d  mov     edx, 0DEh
0x18006b182  mov     r9d, ebx
0x18006b185  call    WPP_SF_d
0x18006b18a  mov     eax, ebx
0x18006b18c  add     rsp, 40h
0x18006b190  pop     r15
0x18006b192  pop     r14
0x18006b194  pop     r13
0x18006b196  pop     rdi
0x18006b197  pop     rsi
0x18006b198  pop     rbp
0x18006b199  pop     rbx
0x18006b19a  retn
```
