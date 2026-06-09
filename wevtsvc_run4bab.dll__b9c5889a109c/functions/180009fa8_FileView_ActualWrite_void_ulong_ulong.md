# FileView::ActualWrite(void *,ulong,ulong)

- ea: `0x180009fa8`
- end: `0x18000a101`
- name: `?ActualWrite@FileView@@AEAAKPEAXKK@Z`
- size: `345`
- prototype: `unsigned int(FileView *__hidden this, void *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180009c5c`
- `0x1800b29b8`
- `0x1800b3998`
- `0x1800b3ea0`

## callees

- `0x180009fa8`
- `0x180092008`

## import_xrefs

- `ntdll!NtWriteFile` at `0x18000a00b`
- `ntdll!NtWriteFile` at `0x18000a00b`
- `ntdll!RtlNtStatusToDosError` at `0x18000a04f`
- `ntdll!RtlNtStatusToDosError` at `0x18000a04f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a05a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a0c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a05a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a0c8`

## pseudocode

```c
__int64 __fastcall FileView::ActualWrite(FileView *this, void *a2, unsigned int a3, ULONG Length)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v8; // rdx
  int v9; // eax
  _QWORD *v11; // rcx
  unsigned int v12; // ebx
  ULONG v13; // eax
  __int64 v14; // rdx
  struct _IO_STATUS_BLOCK v15; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER v16; // [rsp+70h] [rbp+8h] BYREF

  v4 = *((_QWORD *)this + 1);
  v5 = Length;
  v15 = 0;
  if ( v4 == -1 )
  {
    v11 = WPP_GLOBAL_Control;
    v12 = 4317;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v12;
    }
    v14 = 13;
    goto LABEL_14;
  }
  v8 = *((_QWORD *)this + 2);
  v16.QuadPart = a3 + v4;
  v9 = NtWriteFile(a2, 0, 0, 0, &v15, (PVOID)(a3 + v8), Length, &v16, 0);
  if ( v9 < 0 )
  {
    *((_BYTE *)this + 40) = 4;
    v13 = RtlNtStatusToDosError(v9);
    *((_DWORD *)this + 9) = v13;
    SetLastError(v13);
    v12 = *((_DWORD *)this + 9);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v12;
    }
    v14 = 14;
    goto LABEL_14;
  }
  if ( v5 == v15.Information )
    return 0;
  *((_BYTE *)this + 40) = 4;
  *((_DWORD *)this + 9) = 29;
  SetLastError(0x1Du);
  v12 = *((_DWORD *)this + 9);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 15;
LABEL_14:
    WPP_SF_d(v11[2], v14, &WPP_978fcd34fd223a1a0030c3cde256baa0_Traceguids, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180009fa8  mov     r11, rsp
0x180009fab  mov     [r11+10h], rbx
0x180009faf  push    rdi
0x180009fb0  sub     rsp, 60h
0x180009fb4  mov     rax, [rcx+8]
0x180009fb8  xorps   xmm0, xmm0
0x180009fbb  mov     edi, r9d
0x180009fbe  mov     r10, rdx
0x180009fc1  mov     rbx, rcx
0x180009fc4  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x180009fc9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009fcd  jz      short loc_18000A02D
0x180009fcf  mov     rdx, [rbx+10h]
0x180009fd3  xor     r9d, r9d; ApcContext
0x180009fd6  mov     ecx, r8d
0x180009fd9  xor     r8d, r8d; ApcRoutine
0x180009fdc  add     rax, rcx
0x180009fdf  mov     qword ptr [r11-28h], 0
0x180009fe7  add     rdx, rcx
0x180009fea  mov     [r11+8], rax
0x180009fee  lea     rax, [r11+8]
0x180009ff2  mov     rcx, r10; FileHandle
0x180009ff5  mov     [r11-30h], rax
0x180009ff9  lea     rax, [r11-18h]
0x180009ffd  mov     [rsp+68h+Length], edi; Length
0x18000a001  mov     [r11-40h], rdx
0x18000a005  xor     edx, edx; Event
0x18000a007  mov     [r11-48h], rax
0x18000a00b  call    cs:__imp_NtWriteFile
0x18000a011  test    eax, eax
0x18000a013  js      short loc_18000A049
0x18000a015  cmp     rdi, [rsp+68h+var_18.Information]
0x18000a01a  jnz     loc_18000A0BC
0x18000a020  xor     eax, eax
0x18000a022  mov     rbx, [rsp+68h+arg_8]
0x18000a027  add     rsp, 60h
0x18000a02b  pop     rdi
0x18000a02c  retn
0x18000a02d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a034  lea     rax, WPP_GLOBAL_Control
0x18000a03b  mov     ebx, 10DDh
0x18000a040  cmp     rcx, rax
0x18000a043  jnz     short loc_18000A08C
0x18000a045  mov     eax, ebx
0x18000a047  jmp     short loc_18000A022
0x18000a049  mov     ecx, eax; Status
0x18000a04b  mov     byte ptr [rbx+28h], 4
0x18000a04f  call    cs:__imp_RtlNtStatusToDosError
0x18000a055  mov     ecx, eax; dwErrCode
0x18000a057  mov     [rbx+24h], eax
0x18000a05a  call    cs:__imp_SetLastError
0x18000a060  mov     ebx, [rbx+24h]
0x18000a063  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a06a  lea     rax, WPP_GLOBAL_Control
0x18000a071  cmp     rcx, rax
0x18000a074  jz      short loc_18000A045
0x18000a076  test    dword ptr [rcx+1Ch], 8000h
0x18000a07d  jz      short loc_18000A045
0x18000a07f  cmp     byte ptr [rcx+19h], 2
0x18000a083  jb      short loc_18000A045
0x18000a085  mov     edx, 0Eh
0x18000a08a  jmp     short loc_18000A0A7
0x18000a08c  test    dword ptr [rcx+1Ch], 8000h
0x18000a093  jz      short loc_18000A045
0x18000a095  cmp     byte ptr [rcx+19h], 2
0x18000a099  jb      short loc_18000A045
0x18000a09b  mov     edx, 0Dh
0x18000a0a0  jmp     short loc_18000A0A7
0x18000a0a2  mov     edx, 0Fh
0x18000a0a7  mov     rcx, [rcx+10h]
0x18000a0ab  lea     r8, WPP_978fcd34fd223a1a0030c3cde256baa0_Traceguids
0x18000a0b2  mov     r9d, ebx
0x18000a0b5  call    WPP_SF_d
0x18000a0ba  jmp     short loc_18000A045
0x18000a0bc  mov     ecx, 1Dh; dwErrCode
0x18000a0c1  mov     byte ptr [rbx+28h], 4
0x18000a0c5  mov     [rbx+24h], ecx
0x18000a0c8  call    cs:__imp_SetLastError
0x18000a0ce  mov     ebx, [rbx+24h]
0x18000a0d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0d8  lea     rax, WPP_GLOBAL_Control
0x18000a0df  cmp     rcx, rax
0x18000a0e2  jz      loc_18000A045
0x18000a0e8  test    dword ptr [rcx+1Ch], 8000h
0x18000a0ef  jz      loc_18000A045
0x18000a0f5  cmp     byte ptr [rcx+19h], 2
0x18000a0f9  jb      loc_18000A045
0x18000a0ff  jmp     short loc_18000A0A2
```
