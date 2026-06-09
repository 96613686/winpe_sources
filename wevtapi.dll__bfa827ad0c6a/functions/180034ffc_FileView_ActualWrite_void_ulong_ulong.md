# FileView::ActualWrite(void *,ulong,ulong)

- ea: `0x180034ffc`
- end: `0x180035167`
- name: `?ActualWrite@FileView@@AEAAKPEAXKK@Z`
- size: `363`
- prototype: `unsigned int(FileView *__hidden this, void *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1800315f8`
- `0x180032dbc`
- `0x180033078`
- `0x180033f34`

## callees

- `0x180023548`
- `0x180034ffc`

## import_xrefs

- `ntdll!NtWriteFile` at `0x1800350aa`
- `ntdll!NtWriteFile` at `0x1800350aa`
- `ntdll!RtlNtStatusToDosError` at `0x1800350ba`
- `ntdll!RtlNtStatusToDosError` at `0x1800350ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800350c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035119`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800350c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035119`

## pseudocode

```c
__int64 __fastcall FileView::ActualWrite(FileView *this, void *a2, unsigned int a3, ULONG Length)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  LastErrInfo *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v12; // rdx
  int v13; // eax
  ULONG v14; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+70h] [rbp+8h] BYREF

  v4 = *((_QWORD *)this + 1);
  v5 = Length;
  IoStatusBlock = 0;
  if ( v4 == -1 )
  {
    v8 = WPP_GLOBAL_Control;
    v9 = 4317;
    if ( WPP_GLOBAL_Control == (LastErrInfo *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v9;
    }
    v10 = 13;
LABEL_6:
    WPP_SF_D(*((_QWORD *)v8 + 2), v10, WPP_978fcd34fd223a1a0030c3cde256baa0_Traceguids, v9);
    return v9;
  }
  v12 = *((_QWORD *)this + 2);
  ByteOffset.QuadPart = a3 + v4;
  v13 = NtWriteFile(a2, 0, 0, 0, &IoStatusBlock, (PVOID)(a3 + v12), Length, &ByteOffset, 0);
  if ( v13 < 0 )
  {
    *((_BYTE *)this + 40) = 4;
    v14 = RtlNtStatusToDosError(v13);
    *((_DWORD *)this + 9) = v14;
    SetLastError(v14);
    v9 = *((_DWORD *)this + 9);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LastErrInfo *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v9;
    }
    v10 = 14;
    goto LABEL_6;
  }
  if ( v5 != IoStatusBlock.Information )
  {
    *((_BYTE *)this + 40) = 4;
    *((_DWORD *)this + 9) = 29;
    SetLastError(0x1Du);
    v9 = *((_DWORD *)this + 9);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LastErrInfo *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v9;
    }
    v10 = 15;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x180034ffc  mov     [rsp+arg_8], rbx
0x180035001  push    rdi
0x180035002  sub     rsp, 60h
0x180035006  mov     rax, [rcx+8]
0x18003500a  xorps   xmm0, xmm0
0x18003500d  mov     edi, r9d
0x180035010  mov     r10, rdx
0x180035013  mov     rbx, rcx
0x180035016  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x18003501b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003501f  jnz     short loc_180035067
0x180035021  mov     rcx, cs:WPP_GLOBAL_Control
0x180035028  lea     rax, WPP_GLOBAL_Control
0x18003502f  mov     ebx, 10DDh
0x180035034  cmp     rcx, rax
0x180035037  jz      short loc_180035060
0x180035039  test    dword ptr [rcx+1Ch], 8000h
0x180035040  jz      short loc_180035060
0x180035042  cmp     byte ptr [rcx+19h], 2
0x180035046  jb      short loc_180035060
0x180035048  mov     edx, 0Dh
0x18003504d  mov     rcx, [rcx+10h]
0x180035051  lea     r8, WPP_978fcd34fd223a1a0030c3cde256baa0_Traceguids
0x180035058  mov     r9d, ebx
0x18003505b  call    WPP_SF_D
0x180035060  mov     eax, ebx
0x180035062  jmp     loc_18003515C
0x180035067  mov     rdx, [rbx+10h]
0x18003506b  xor     r9d, r9d; ApcContext
0x18003506e  mov     ecx, r8d
0x180035071  xor     r8d, r8d; ApcRoutine
0x180035074  add     rax, rcx
0x180035077  mov     [rsp+68h+Key], 0; Key
0x180035080  add     rdx, rcx
0x180035083  mov     qword ptr [rsp+68h+arg_0], rax
0x180035088  lea     rax, [rsp+68h+arg_0]
0x18003508d  mov     rcx, r10; FileHandle
0x180035090  mov     [rsp+68h+ByteOffset], rax; ByteOffset
0x180035095  lea     rax, [rsp+68h+var_18]
0x18003509a  mov     [rsp+68h+Length], edi; Length
0x18003509e  mov     [rsp+68h+Buffer], rdx; Buffer
0x1800350a3  xor     edx, edx; Event
0x1800350a5  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1800350aa  call    cs:__imp_NtWriteFile
0x1800350b0  test    eax, eax
0x1800350b2  jns     short loc_180035106
0x1800350b4  mov     ecx, eax; Status
0x1800350b6  mov     byte ptr [rbx+28h], 4
0x1800350ba  call    cs:__imp_RtlNtStatusToDosError
0x1800350c0  mov     ecx, eax; dwErrCode
0x1800350c2  mov     [rbx+24h], eax
0x1800350c5  call    cs:__imp_SetLastError
0x1800350cb  mov     ebx, [rbx+24h]
0x1800350ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800350d5  lea     rax, WPP_GLOBAL_Control
0x1800350dc  cmp     rcx, rax
0x1800350df  jz      loc_180035060
0x1800350e5  test    dword ptr [rcx+1Ch], 8000h
0x1800350ec  jz      loc_180035060
0x1800350f2  cmp     byte ptr [rcx+19h], 2
0x1800350f6  jb      loc_180035060
0x1800350fc  mov     edx, 0Eh
0x180035101  jmp     loc_18003504D
0x180035106  cmp     rdi, [rsp+68h+var_18.Information]
0x18003510b  jz      short loc_18003515A
0x18003510d  mov     ecx, 1Dh; dwErrCode
0x180035112  mov     byte ptr [rbx+28h], 4
0x180035116  mov     [rbx+24h], ecx
0x180035119  call    cs:__imp_SetLastError
0x18003511f  mov     ebx, [rbx+24h]
0x180035122  mov     rcx, cs:WPP_GLOBAL_Control
0x180035129  lea     rax, WPP_GLOBAL_Control
0x180035130  cmp     rcx, rax
0x180035133  jz      loc_180035060
0x180035139  test    dword ptr [rcx+1Ch], 8000h
0x180035140  jz      loc_180035060
0x180035146  cmp     byte ptr [rcx+19h], 2
0x18003514a  jb      loc_180035060
0x180035150  mov     edx, 0Fh
0x180035155  jmp     loc_18003504D
0x18003515a  xor     eax, eax
0x18003515c  mov     rbx, [rsp+68h+arg_8]
0x180035161  add     rsp, 60h
0x180035165  pop     rdi
0x180035166  retn
```
