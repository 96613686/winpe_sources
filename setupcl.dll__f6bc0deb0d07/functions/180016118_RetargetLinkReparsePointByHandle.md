# RetargetLinkReparsePointByHandle

- ea: `0x180016118`
- end: `0x180016339`
- name: `RetargetLinkReparsePointByHandle`
- size: `545`
- prototype: `__int64 __fastcall(char *Handle, const wchar_t *, const wchar_t *, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x180010b08`

## callees

- `0x1800156f8`
- `0x180015f7c`
- `0x180016088`
- `0x180016118`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180016181`
- `ntdll!RtlAdjustPrivilege` at `0x18001619f`
- `ntdll!RtlAdjustPrivilege` at `0x1800162b1`
- `ntdll!RtlAdjustPrivilege` at `0x1800162cf`
- `ntdll!RtlAdjustPrivilege` at `0x180016181`
- `ntdll!RtlAdjustPrivilege` at `0x18001619f`
- `ntdll!RtlAdjustPrivilege` at `0x1800162b1`
- `ntdll!RtlAdjustPrivilege` at `0x1800162cf`
- `ntdll!RtlFreeHeap` at `0x180016293`
- `ntdll!RtlFreeHeap` at `0x180016293`
- `ntdll!NtFsControlFile` at `0x180016249`
- `ntdll!NtFsControlFile` at `0x180016249`
- `ntdll!NtWaitForSingleObject` at `0x180016260`
- `ntdll!NtWaitForSingleObject` at `0x180016260`

## string_xrefs

- `0x1800161ea`: `FixReparsePointPath: Ignoring reparse point with tag [0x%X].`

## pseudocode

```c
__int64 __fastcall RetargetLinkReparsePointByHandle(char *Handle, const wchar_t *a2, const wchar_t *a3, _DWORD *a4)
{
  bool v8; // r13
  int ReparsePointData; // eax
  PVOID InputBuffer; // rsi
  NTSTATUS Status; // ebx
  int v12; // eax
  int fixed; // eax
  unsigned int v15; // eax
  unsigned __int8 v16; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int8 v17[3]; // [rsp+51h] [rbp-18h] BYREF
  ULONG InputBufferLength; // [rsp+54h] [rbp-15h] BYREF
  int v19; // [rsp+58h] [rbp-11h] BYREF
  int v20; // [rsp+5Ch] [rbp-Dh] BYREF
  BOOL v21; // [rsp+60h] [rbp-9h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int8 OldValue; // [rsp+D0h] [rbp+67h] BYREF

  OldValue = 0;
  v16 = 0;
  v17[0] = 0;
  v19 = 0;
  IoStatusBlock.Pointer = 0;
  InputBufferLength = 0;
  v20 = 0;
  if ( (unsigned __int64)(Handle - 1) > 0xFFFFFFFFFFFFFFFDuLL || !a3 )
    return 3221225485LL;
  if ( a4 )
    *a4 = 0;
  v8 = RtlAdjustPrivilege(0x11u, 1u, 0, &OldValue) >= 0;
  v21 = RtlAdjustPrivilege(0x12u, 1u, 0, &v16) >= 0;
  ReparsePointData = GetReparsePointData(Handle, &IoStatusBlock, &InputBufferLength, &v20);
  InputBuffer = IoStatusBlock.Pointer;
  Status = ReparsePointData;
  if ( ReparsePointData >= 0 )
  {
    if ( *(_DWORD *)IoStatusBlock.Pointer == -1610612733 || *(_DWORD *)IoStatusBlock.Pointer == -1610612724 )
    {
      fixed = FixReparsePointPath((unsigned int *)IoStatusBlock.Pointer, &InputBufferLength, &v20, a2, a3, &v19);
      if ( fixed < 0 )
      {
        Status = (unsigned __int16)fixed;
        v15 = (unsigned __int16)fixed | 0xC0070000;
        if ( Status )
          Status = v15;
        if ( Status >= 0 )
          Status = -1073741823;
        goto LABEL_17;
      }
    }
    else
    {
      LibLog(
        &g_WdsNativeLibLog,
        50331648,
        L"FixReparsePointPath: Ignoring reparse point with tag [0x%X].",
        *(unsigned int *)IoStatusBlock.Pointer);
    }
    v12 = v19;
    if ( v19 )
    {
      IoStatusBlock = 0;
      Status = NtFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x900A4u, InputBuffer, InputBufferLength, 0, 0);
      if ( Status == 259 )
      {
        Status = NtWaitForSingleObject(Handle, 0, 0);
        if ( Status >= 0 )
          Status = IoStatusBlock.Status;
      }
      if ( Status < 0 )
        goto LABEL_17;
      v12 = v19;
    }
    if ( a4 )
      *a4 = v12;
  }
LABEL_17:
  if ( InputBuffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, InputBuffer);
  if ( v8 && !OldValue )
    RtlAdjustPrivilege(0x11u, 0, 0, v17);
  if ( v21 && !v16 )
    RtlAdjustPrivilege(0x12u, 0, 0, v17);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x180016118  push    rbp
0x18001611a  push    rbx
0x18001611b  push    rsi
0x18001611c  push    rdi
0x18001611d  push    r12
0x18001611f  push    r13
0x180016121  push    r14
0x180016123  push    r15
0x180016125  lea     rbp, [rsp-1Fh]
0x18001612a  sub     rsp, 88h
0x180016131  mov     r14, rcx
0x180016134  mov     rdi, r9
0x180016137  xor     ecx, ecx
0x180016139  mov     r15, r8
0x18001613c  mov     r12, rdx
0x18001613f  mov     [rbp+57h+OldValue], cl
0x180016142  mov     [rbp+57h+var_70], cl
0x180016145  lea     rax, [r14-1]
0x180016149  mov     [rbp+57h+var_6F], cl
0x18001614c  mov     [rbp+57h+var_68], ecx
0x18001614f  mov     qword ptr [rbp+57h+var_58], rcx
0x180016153  mov     [rbp+57h+var_6C], ecx
0x180016156  mov     [rbp+57h+var_64], ecx
0x180016159  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001615d  ja      loc_180016320
0x180016163  test    r8, r8
0x180016166  jz      loc_180016320
0x18001616c  test    r9, r9
0x18001616f  jz      short loc_180016174
0x180016171  mov     [r9], ecx
0x180016174  xor     r8d, r8d; ForThread
0x180016177  lea     r9, [rbp+57h+OldValue]; OldValue
0x18001617b  mov     dl, 1; NewValue
0x18001617d  lea     ecx, [r8+11h]; Privilege
0x180016181  call    cs:__imp_RtlAdjustPrivilege
0x180016187  xor     r8d, r8d; ForThread
0x18001618a  lea     r9, [rbp+57h+var_70]; OldValue
0x18001618e  mov     r13d, eax
0x180016191  mov     dl, 1; NewValue
0x180016193  shr     r13d, 1Fh
0x180016197  xor     r13b, 1
0x18001619b  lea     ecx, [r8+12h]; Privilege
0x18001619f  call    cs:__imp_RtlAdjustPrivilege
0x1800161a5  shr     eax, 1Fh
0x1800161a8  lea     r9, [rbp+57h+var_64]
0x1800161ac  lea     r8, [rbp+57h+var_6C]
0x1800161b0  mov     rcx, r14; Handle
0x1800161b3  xor     al, 1
0x1800161b5  lea     rdx, [rbp+57h+var_58]
0x1800161b9  mov     [rbp+57h+var_60], eax
0x1800161bc  call    GetReparsePointData
0x1800161c1  mov     rsi, qword ptr [rbp+57h+var_58]
0x1800161c5  mov     ebx, eax
0x1800161c7  test    eax, eax
0x1800161c9  js      loc_18001627C
0x1800161cf  cmp     dword ptr [rsi], 0A0000003h
0x1800161d5  jz      loc_1800162D9
0x1800161db  cmp     dword ptr [rsi], 0A000000Ch
0x1800161e1  jz      loc_1800162D9
0x1800161e7  mov     r9d, [rsi]
0x1800161ea  lea     r8, aFixreparsepoin; "FixReparsePointPath: Ignoring reparse p"...
0x1800161f1  mov     edx, 3000000h
0x1800161f6  lea     rcx, g_WdsNativeLibLog
0x1800161fd  call    LibLog
0x180016202  mov     eax, [rbp+57h+var_68]
0x180016205  test    eax, eax
0x180016207  jz      short loc_180016275
0x180016209  mov     eax, [rbp+57h+var_6C]
0x18001620c  xorps   xmm0, xmm0
0x18001620f  mov     [rsp+0C0h+OutputBufferLength], 0; OutputBufferLength
0x180016217  xor     r9d, r9d; ApcContext
0x18001621a  mov     [rsp+0C0h+OutputBuffer], 0; OutputBuffer
0x180016223  xor     r8d, r8d; ApcRoutine
0x180016226  mov     [rsp+0C0h+InputBufferLength], eax; InputBufferLength
0x18001622a  xor     edx, edx; Event
0x18001622c  mov     [rsp+0C0h+InputBuffer], rsi; InputBuffer
0x180016231  lea     rax, [rbp+57h+var_58]
0x180016235  mov     [rsp+0C0h+FsControlCode], 900A4h; FsControlCode
0x18001623d  mov     rcx, r14; FileHandle
0x180016240  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x180016245  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180016249  call    cs:__imp_NtFsControlFile
0x18001624f  mov     ebx, eax
0x180016251  cmp     eax, 103h
0x180016256  jnz     short loc_18001626E
0x180016258  xor     r8d, r8d; Timeout
0x18001625b  xor     edx, edx; Alertable
0x18001625d  mov     rcx, r14; Handle
0x180016260  call    cs:__imp_NtWaitForSingleObject
0x180016266  test    eax, eax
0x180016268  mov     ebx, eax
0x18001626a  cmovns  ebx, dword ptr [rbp+57h+var_58]
0x18001626e  test    ebx, ebx
0x180016270  js      short loc_18001627C
0x180016272  mov     eax, [rbp+57h+var_68]
0x180016275  test    rdi, rdi
0x180016278  jz      short loc_18001627C
0x18001627a  mov     [rdi], eax
0x18001627c  test    rsi, rsi
0x18001627f  jz      short loc_180016299
0x180016281  mov     rcx, gs:60h
0x18001628a  mov     r8, rsi; P
0x18001628d  xor     edx, edx; Flags
0x18001628f  mov     rcx, [rcx+30h]; HeapHandle
0x180016293  call    cs:__imp_RtlFreeHeap
0x180016299  cmp     r13b, 1
0x18001629d  jnz     short loc_1800162B7
0x18001629f  cmp     [rbp+57h+OldValue], 0
0x1800162a3  jnz     short loc_1800162B7
0x1800162a5  xor     edx, edx; NewValue
0x1800162a7  lea     r9, [rbp+57h+var_6F]; OldValue
0x1800162ab  xor     r8d, r8d; ForThread
0x1800162ae  lea     ecx, [rdx+11h]; Privilege
0x1800162b1  call    cs:__imp_RtlAdjustPrivilege
0x1800162b7  cmp     byte ptr [rbp+57h+var_60], 1
0x1800162bb  jnz     short loc_1800162D5
0x1800162bd  cmp     [rbp+57h+var_70], 0
0x1800162c1  jnz     short loc_1800162D5
0x1800162c3  xor     edx, edx; NewValue
0x1800162c5  lea     r9, [rbp+57h+var_6F]; OldValue
0x1800162c9  xor     r8d, r8d; ForThread
0x1800162cc  lea     ecx, [rdx+12h]; Privilege
0x1800162cf  call    cs:__imp_RtlAdjustPrivilege
0x1800162d5  mov     eax, ebx
0x1800162d7  jmp     short loc_180016325
0x1800162d9  lea     rax, [rbp+57h+var_68]
0x1800162dd  mov     r9, r12
0x1800162e0  mov     qword ptr [rsp+0C0h+FsControlCode], rax
0x1800162e5  lea     r8, [rbp+57h+var_64]
0x1800162e9  lea     rdx, [rbp+57h+var_6C]
0x1800162ed  mov     [rsp+0C0h+IoStatusBlock], r15
0x1800162f2  mov     rcx, rsi
0x1800162f5  call    FixReparsePointPath
0x1800162fa  test    eax, eax
0x1800162fc  jns     loc_180016202
0x180016302  movzx   ebx, ax
0x180016305  mov     eax, ebx
0x180016307  or      eax, 0C0070000h
0x18001630c  test    ebx, ebx
0x18001630e  cmovnz  ebx, eax
0x180016311  mov     eax, 0C0000001h
0x180016316  test    ebx, ebx
0x180016318  cmovns  ebx, eax
0x18001631b  jmp     loc_18001627C
0x180016320  mov     eax, 0C000000Dh
0x180016325  add     rsp, 88h
0x18001632c  pop     r15
0x18001632e  pop     r14
0x180016330  pop     r13
0x180016332  pop     r12
0x180016334  pop     rdi
0x180016335  pop     rsi
0x180016336  pop     rbx
0x180016337  pop     rbp
0x180016338  retn
```
