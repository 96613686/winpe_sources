# FileView::ReadIn(void *,unsigned __int64)

- ea: `0x180035170`
- end: `0x18003528a`
- name: `?ReadIn@FileView@@QEAAXPEAX_K@Z`
- size: `282`
- prototype: `void(FileView *__hidden this, void *, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800315f8`
- `0x180032704`
- `0x180032bd0`
- `0x180032c8c`
- `0x1800340a8`
- `0x18003459c`

## callees

- `0x180023548`
- `0x180035170`
- `0x180038fa4`

## import_xrefs

- `ntdll!NtReadFile` at `0x1800351c6`
- `ntdll!NtReadFile` at `0x1800351c6`
- `ntdll!RtlNtStatusToDosError` at `0x1800351e2`
- `ntdll!RtlNtStatusToDosError` at `0x1800351e2`
- `ntdll!RtlSetLastWin32Error` at `0x1800351ed`
- `ntdll!RtlSetLastWin32Error` at `0x1800351ed`

## pseudocode

```c
void __fastcall FileView::ReadIn(union _LARGE_INTEGER *this, void *a2, union _LARGE_INTEGER a3)
{
  int v5; // eax
  ULONG v6; // eax
  unsigned int HighPart; // ebx
  void *QuadPart; // [rsp+28h] [rbp-70h]
  ULONG Length; // [rsp+30h] [rbp-68h]
  struct _IO_STATUS_BLOCK v10; // [rsp+50h] [rbp-48h] BYREF
  __int128 pExceptionObject; // [rsp+60h] [rbp-38h] BYREF
  __int64 v12; // [rsp+70h] [rbp-28h]
  unsigned int v13; // [rsp+78h] [rbp-20h]
  int v14; // [rsp+7Ch] [rbp-1Ch]
  int v15; // [rsp+80h] [rbp-18h]
  union _LARGE_INTEGER v16; // [rsp+A0h] [rbp+8h] BYREF

  Length = this[4].LowPart;
  QuadPart = (void *)this[2].QuadPart;
  v16 = a3;
  v10 = 0;
  v5 = NtReadFile(a2, 0, 0, 0, &v10, QuadPart, Length, &v16, 0);
  if ( v5 < 0 )
  {
    this[1].QuadPart = -1;
    LOBYTE(this[5].LowPart) = 2;
    v6 = RtlNtStatusToDosError(v5);
    this[4].HighPart = v6;
    RtlSetLastWin32Error(v6);
    HighPart = this[4].HighPart;
    if ( !HighPart )
      HighPart = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_978fcd34fd223a1a0030c3cde256baa0_Traceguids, HighPart);
    }
    v12 = 0;
    v13 = HighPart;
    v14 = -1;
    pExceptionObject = 0;
    v15 = 112;
    throw (EvtException *)&pExceptionObject;
  }
  this[1] = a3;
}

```

## disassembly

```asm
0x180035170  mov     r11, rsp
0x180035173  mov     [r11+10h], rbx
0x180035177  push    rdi
0x180035178  sub     rsp, 90h
0x18003517f  mov     qword ptr [r11-58h], 0
0x180035187  lea     rax, [r11+8]
0x18003518b  mov     [r11-60h], rax
0x18003518f  mov     r10, rdx
0x180035192  mov     eax, [rcx+20h]
0x180035195  mov     rdi, r8
0x180035198  mov     [rsp+98h+Length], eax; Length
0x18003519c  mov     rbx, rcx
0x18003519f  mov     rax, [rcx+10h]
0x1800351a3  xorps   xmm0, xmm0
0x1800351a6  mov     [r11-70h], rax
0x1800351aa  xor     r9d, r9d; ApcContext
0x1800351ad  lea     rax, [r11-48h]
0x1800351b1  mov     [r11+8], r8
0x1800351b5  xor     r8d, r8d; ApcRoutine
0x1800351b8  mov     [r11-78h], rax
0x1800351bc  xor     edx, edx; Event
0x1800351be  mov     rcx, r10; FileHandle
0x1800351c1  movups  [rsp+98h+var_48], xmm0
0x1800351c6  call    cs:__imp_NtReadFile
0x1800351cc  test    eax, eax
0x1800351ce  jns     loc_180035275
0x1800351d4  mov     ecx, eax; Status
0x1800351d6  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800351de  mov     byte ptr [rbx+28h], 2
0x1800351e2  call    cs:__imp_RtlNtStatusToDosError
0x1800351e8  mov     ecx, eax; LastError
0x1800351ea  mov     [rbx+24h], eax
0x1800351ed  call    cs:__imp_RtlSetLastWin32Error
0x1800351f3  mov     ebx, [rbx+24h]
0x1800351f6  mov     eax, 507h
0x1800351fb  test    ebx, ebx
0x1800351fd  cmovz   ebx, eax
0x180035200  mov     rcx, cs:WPP_GLOBAL_Control
0x180035207  lea     rax, WPP_GLOBAL_Control
0x18003520e  cmp     rcx, rax
0x180035211  jz      short loc_18003523A
0x180035213  test    dword ptr [rcx+1Ch], 8000h
0x18003521a  jz      short loc_18003523A
0x18003521c  cmp     byte ptr [rcx+19h], 2
0x180035220  jb      short loc_18003523A
0x180035222  mov     rcx, [rcx+10h]
0x180035226  lea     r8, WPP_978fcd34fd223a1a0030c3cde256baa0_Traceguids
0x18003522d  mov     edx, 0Ch
0x180035232  mov     r9d, ebx
0x180035235  call    WPP_SF_D
0x18003523a  xorps   xmm0, xmm0
0x18003523d  mov     [rsp+98h+var_28], 0
0x180035246  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003524d  mov     [rsp+98h+var_20], ebx
0x180035251  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180035256  mov     [rsp+98h+var_1C], 0FFFFFFFFh
0x18003525e  movdqu  [rsp+98h+pExceptionObject], xmm0
0x180035264  mov     [rsp+98h+var_18], 70h ; 'p'
0x18003526f  call    _CxxThrowException_0
0x180035275  mov     [rbx+8], rdi
0x180035279  mov     rbx, [rsp+98h+arg_8]
0x180035281  add     rsp, 90h
0x180035288  pop     rdi
0x180035289  retn
```
