# FileView::ReadIn(void *,unsigned __int64)

- ea: `0x180064738`
- end: `0x18006484e`
- name: `?ReadIn@FileView@@QEAAXPEAX_K@Z`
- size: `278`
- prototype: `void __fastcall(union _LARGE_INTEGER *this, void *, union _LARGE_INTEGER)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800098bc`
- `0x18000b8f4`
- `0x180041a00`
- `0x18007f4dc`
- `0x1800b29b8`
- `0x1800b3800`
- `0x1800b4008`

## callees

- `0x180064738`
- `0x180092008`
- `0x1800d334c`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800647c6`
- `ntdll!RtlSetLastWin32Error` at `0x1800647c6`
- `ntdll!NtReadFile` at `0x18006478e`
- `ntdll!NtReadFile` at `0x18006478e`
- `ntdll!RtlNtStatusToDosError` at `0x1800647bb`
- `ntdll!RtlNtStatusToDosError` at `0x1800647bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_978fcd34fd223a1a0030c3cde256baa0_Traceguids, HighPart);
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
0x180064738  mov     r11, rsp
0x18006473b  mov     [r11+10h], rbx
0x18006473f  push    rdi
0x180064740  sub     rsp, 90h
0x180064747  mov     qword ptr [r11-58h], 0
0x18006474f  lea     rax, [r11+8]
0x180064753  mov     [r11-60h], rax
0x180064757  mov     r10, rdx
0x18006475a  mov     eax, [rcx+20h]
0x18006475d  mov     rdi, r8
0x180064760  mov     [rsp+98h+Length], eax; Length
0x180064764  mov     rbx, rcx
0x180064767  mov     rax, [rcx+10h]
0x18006476b  xorps   xmm0, xmm0
0x18006476e  mov     [r11-70h], rax
0x180064772  xor     r9d, r9d; ApcContext
0x180064775  lea     rax, [r11-48h]
0x180064779  mov     [r11+8], r8
0x18006477d  xor     r8d, r8d; ApcRoutine
0x180064780  mov     [r11-78h], rax
0x180064784  xor     edx, edx; Event
0x180064786  mov     rcx, r10; FileHandle
0x180064789  movups  [rsp+98h+var_48], xmm0
0x18006478e  call    cs:__imp_NtReadFile
0x180064794  test    eax, eax
0x180064796  js      short loc_1800647AD
0x180064798  mov     [rbx+8], rdi
0x18006479c  mov     rbx, [rsp+98h+arg_8]
0x1800647a4  add     rsp, 90h
0x1800647ab  pop     rdi
0x1800647ac  retn
0x1800647ad  mov     ecx, eax; Status
0x1800647af  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800647b7  mov     byte ptr [rbx+28h], 2
0x1800647bb  call    cs:__imp_RtlNtStatusToDosError
0x1800647c1  mov     ecx, eax; LastError
0x1800647c3  mov     [rbx+24h], eax
0x1800647c6  call    cs:__imp_RtlSetLastWin32Error
0x1800647cc  mov     ebx, [rbx+24h]
0x1800647cf  mov     eax, 507h
0x1800647d4  test    ebx, ebx
0x1800647d6  cmovz   ebx, eax
0x1800647d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800647e0  lea     rax, WPP_GLOBAL_Control
0x1800647e7  cmp     rcx, rax
0x1800647ea  jz      short loc_180064813
0x1800647ec  test    dword ptr [rcx+1Ch], 8000h
0x1800647f3  jz      short loc_180064813
0x1800647f5  cmp     byte ptr [rcx+19h], 2
0x1800647f9  jb      short loc_180064813
0x1800647fb  mov     rcx, [rcx+10h]
0x1800647ff  lea     r8, WPP_978fcd34fd223a1a0030c3cde256baa0_Traceguids
0x180064806  mov     edx, 0Ch
0x18006480b  mov     r9d, ebx
0x18006480e  call    WPP_SF_d
0x180064813  xorps   xmm0, xmm0
0x180064816  mov     [rsp+98h+var_28], 0
0x18006481f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180064826  mov     [rsp+98h+var_20], ebx
0x18006482a  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18006482f  mov     [rsp+98h+var_1C], 0FFFFFFFFh
0x180064837  movdqu  [rsp+98h+pExceptionObject], xmm0
0x18006483d  mov     [rsp+98h+var_18], 70h ; 'p'
0x180064848  call    _CxxThrowException_0
```
