# DavDeleteUserEntries

- ea: `0x180003f8c`
- end: `0x180004281`
- name: `DavDeleteUserEntries`
- size: `757`
- prototype: `void()`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000fb90`

## callees

- `0x180003a9c`
- `0x180003f8c`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000bc5c`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x1800040b9`
- `ntdll!NtFsControlFile` at `0x1800040b9`
- `ntdll!RtlAcquireResourceExclusive` at `0x180003fa2`
- `ntdll!RtlAcquireResourceExclusive` at `0x180003fa2`
- `ntdll!NtClose` at `0x180004137`
- `ntdll!NtClose` at `0x180004137`
- `ntdll!RtlReleaseResource` at `0x18000426e`
- `ntdll!RtlReleaseResource` at `0x18000426e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000404a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004171`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000404a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004171`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041e9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180004040`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180004040`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180004167`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180004167`
- `KERNEL32!LocalFree` at `0x180004201`
- `KERNEL32!LocalFree` at `0x180004216`
- `KERNEL32!LocalFree` at `0x18000424c`
- `KERNEL32!LocalFree` at `0x180004201`
- `KERNEL32!LocalFree` at `0x180004216`
- `KERNEL32!LocalFree` at `0x18000424c`
- `KERNEL32!LocalUnlock` at `0x18000423f`
- `KERNEL32!LocalUnlock` at `0x18000423f`

## pseudocode

```c
void DavDeleteUserEntries()
{
  unsigned int v0; // ebp
  _QWORD *v1; // r14
  _QWORD *v2; // rbx
  DWORD LastError; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  NTSTATUS v6; // eax
  __int64 Status; // r9
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // eax
  unsigned int v11; // eax
  _DWORD *v12; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-48h] BYREF
  int InputBuffer; // [rsp+A0h] [rbp+8h] BYREF

  if ( !RtlAcquireResourceExclusive(&Resource, 1u) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
    return;
  }
  v0 = 0;
  if ( !dword_180036F60 )
    goto LABEL_44;
  do
  {
    v1 = *(_QWORD **)(DavUseObject + 16LL * v0);
    *(_QWORD *)(DavUseObject + 16LL * v0) = 0;
    while ( v1 )
    {
      InputBuffer = 2;
      v2 = v1;
      IoStatusBlock = 0;
      v1 = (_QWORD *)*v1;
      if ( !SetThreadToken(0, (HANDLE)v2[10]) )
      {
        LastError = GetLastError();
        if ( LastError )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v5 = 232;
LABEL_34:
            WPP_SF_d(v4[2], v5, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
            goto LABEL_35;
          }
        }
        goto LABEL_35;
      }
      v6 = NtFsControlFile((HANDLE)v2[5], 0, 0, 0, &IoStatusBlock, 0x4000020u, &InputBuffer, 4u, 0, 0);
      if ( v6 < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_25;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_22;
        v9 = 234;
        Status = (unsigned int)v6;
        goto LABEL_20;
      }
      Status = (unsigned int)IoStatusBlock.Status;
      if ( !IoStatusBlock.Status )
        goto LABEL_21;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_25;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 233;
LABEL_20:
        WPP_SF_d(v8[2], v9, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, Status);
LABEL_21:
        v8 = WPP_GLOBAL_Control;
      }
LABEL_22:
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 )
        WPP_SF_q(v8[2], 235, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v2[5]);
LABEL_25:
      v10 = NtClose((HANDLE)v2[5]);
      if ( v10
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v10);
      }
      if ( !RevertToSelf() )
      {
        LastError = GetLastError();
        if ( LastError )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v5 = 237;
            goto LABEL_34;
          }
        }
      }
LABEL_35:
      v11 = DavDeleteSymbolicLink((WCHAR *)v2[3], (LPCWSTR)v2[6], (WCHAR *)v2[9], (HANDLE)v2[10], 0);
      if ( v11
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 238, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v11);
      }
      CloseHandle((HANDLE)v2[10]);
      *(_DWORD *)v2[2] -= *((_DWORD *)v2 + 9);
      v12 = (_DWORD *)v2[2];
      if ( !*v12 )
        LocalFree(v12);
      v2[7] = 0;
      *((_DWORD *)v2 + 16) = 0;
      v2[9] = 0;
      LocalFree(v2);
    }
    ++v0;
  }
  while ( v0 < dword_180036F60 );
LABEL_44:
  if ( hMem )
  {
    LocalUnlock(hMem);
    LocalFree(hMem);
    DavUseObject = 0;
    dword_180036F60 = 0;
    hMem = 0;
  }
  RtlReleaseResource(&Resource);
}

```

## disassembly

```asm
0x180003f8c  push    rbx
0x180003f8e  push    rbp
0x180003f8f  push    rsi
0x180003f90  push    rdi
0x180003f91  push    r14
0x180003f93  push    r15
0x180003f95  sub     rsp, 68h
0x180003f99  mov     dl, 1; Wait
0x180003f9b  lea     rcx, Resource; Resource
0x180003fa2  call    cs:__imp_RtlAcquireResourceExclusive
0x180003fa8  xor     r15d, r15d
0x180003fab  test    al, al
0x180003fad  jnz     short loc_180003FEA
0x180003faf  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fb6  lea     rdi, WPP_GLOBAL_Control
0x180003fbd  cmp     rcx, rdi
0x180003fc0  jz      loc_180004274
0x180003fc6  test    byte ptr [rcx+1Ch], 1
0x180003fca  jz      loc_180004274
0x180003fd0  mov     rcx, [rcx+10h]
0x180003fd4  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180003fdb  mov     edx, 0E7h
0x180003fe0  call    WPP_SF_
0x180003fe5  jmp     loc_180004274
0x180003fea  cmp     cs:dword_180036F60, r15d
0x180003ff1  mov     ebp, r15d
0x180003ff4  jbe     loc_180004233
0x180003ffa  lea     rdi, WPP_GLOBAL_Control
0x180004001  lea     rsi, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180004008  mov     rax, cs:DavUseObject
0x18000400f  mov     ecx, ebp
0x180004011  add     rcx, rcx
0x180004014  mov     r14, [rax+rcx*8]
0x180004018  mov     [rax+rcx*8], r15
0x18000401c  jmp     loc_18000421C
0x180004021  mov     [rsp+98h+arg_0], 2
0x18000402c  mov     rbx, r14
0x18000402f  xorps   xmm0, xmm0
0x180004032  xor     ecx, ecx; Thread
0x180004034  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x180004039  mov     r14, [r14]
0x18000403c  mov     rdx, [rbx+50h]; Token
0x180004040  call    cs:__imp_SetThreadToken
0x180004046  test    eax, eax
0x180004048  jnz     short loc_18000407C
0x18000404a  call    cs:__imp_GetLastError
0x180004050  test    eax, eax
0x180004052  jz      loc_1800041A1
0x180004058  mov     rcx, cs:WPP_GLOBAL_Control
0x18000405f  cmp     rcx, rdi
0x180004062  jz      loc_1800041A1
0x180004068  test    byte ptr [rcx+1Ch], 1
0x18000406c  jz      loc_1800041A1
0x180004072  mov     edx, 0E8h
0x180004077  jmp     loc_180004192
0x18000407c  mov     rcx, [rbx+28h]; FileHandle
0x180004080  lea     rax, [rsp+98h+arg_0]
0x180004088  mov     [rsp+98h+OutputBufferLength], r15d; OutputBufferLength
0x18000408d  xor     r9d, r9d; ApcContext
0x180004090  mov     [rsp+98h+OutputBuffer], r15; OutputBuffer
0x180004095  xor     r8d, r8d; ApcRoutine
0x180004098  mov     [rsp+98h+InputBufferLength], 4; InputBufferLength
0x1800040a0  xor     edx, edx; Event
0x1800040a2  mov     [rsp+98h+InputBuffer], rax; InputBuffer
0x1800040a7  lea     rax, [rsp+98h+var_48]
0x1800040ac  mov     [rsp+98h+FsControlCode], 4000020h; FsControlCode
0x1800040b4  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x1800040b9  call    cs:__imp_NtFsControlFile
0x1800040bf  test    eax, eax
0x1800040c1  js      short loc_1800040E6
0x1800040c3  mov     r9d, dword ptr [rsp+98h+var_48]
0x1800040c8  test    r9d, r9d
0x1800040cb  jz      short loc_18000410C
0x1800040cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040d4  cmp     rcx, rdi
0x1800040d7  jz      short loc_180004133
0x1800040d9  test    byte ptr [rcx+1Ch], 1
0x1800040dd  jz      short loc_180004113
0x1800040df  mov     edx, 0E9h
0x1800040e4  jmp     short loc_180004100
0x1800040e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040ed  cmp     rcx, rdi
0x1800040f0  jz      short loc_180004133
0x1800040f2  test    byte ptr [rcx+1Ch], 1
0x1800040f6  jz      short loc_180004113
0x1800040f8  mov     edx, 0EAh
0x1800040fd  mov     r9d, eax
0x180004100  mov     rcx, [rcx+10h]
0x180004104  mov     r8, rsi
0x180004107  call    WPP_SF_d
0x18000410c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004113  cmp     rcx, rdi
0x180004116  jz      short loc_180004133
0x180004118  test    byte ptr [rcx+1Ch], 2
0x18000411c  jz      short loc_180004133
0x18000411e  mov     r9, [rbx+28h]
0x180004122  mov     edx, 0EBh
0x180004127  mov     rcx, [rcx+10h]
0x18000412b  mov     r8, rsi
0x18000412e  call    WPP_SF_q
0x180004133  mov     rcx, [rbx+28h]; Handle
0x180004137  call    cs:__imp_NtClose
0x18000413d  test    eax, eax
0x18000413f  jz      short loc_180004167
0x180004141  mov     rcx, cs:WPP_GLOBAL_Control
0x180004148  cmp     rcx, rdi
0x18000414b  jz      short loc_180004167
0x18000414d  test    byte ptr [rcx+1Ch], 1
0x180004151  jz      short loc_180004167
0x180004153  mov     rcx, [rcx+10h]
0x180004157  mov     edx, 0ECh
0x18000415c  mov     r9d, eax
0x18000415f  mov     r8, rsi
0x180004162  call    WPP_SF_d
0x180004167  call    cs:__imp_RevertToSelf
0x18000416d  test    eax, eax
0x18000416f  jnz     short loc_1800041A1
0x180004171  call    cs:__imp_GetLastError
0x180004177  test    eax, eax
0x180004179  jz      short loc_1800041A1
0x18000417b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004182  cmp     rcx, rdi
0x180004185  jz      short loc_1800041A1
0x180004187  test    byte ptr [rcx+1Ch], 1
0x18000418b  jz      short loc_1800041A1
0x18000418d  mov     edx, 0EDh
0x180004192  mov     rcx, [rcx+10h]
0x180004196  mov     r9d, eax
0x180004199  mov     r8, rsi
0x18000419c  call    WPP_SF_d
0x1800041a1  mov     r9, [rbx+50h]; Token
0x1800041a5  mov     r8, [rbx+48h]; lpDeviceName
0x1800041a9  mov     rdx, [rbx+30h]; lpTargetPath
0x1800041ad  mov     rcx, [rbx+18h]; hMem
0x1800041b1  mov     dword ptr [rsp+98h+IoStatusBlock], r15d; int
0x1800041b6  call    DavDeleteSymbolicLink
0x1800041bb  test    eax, eax
0x1800041bd  jz      short loc_1800041E5
0x1800041bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041c6  cmp     rcx, rdi
0x1800041c9  jz      short loc_1800041E5
0x1800041cb  test    byte ptr [rcx+1Ch], 1
0x1800041cf  jz      short loc_1800041E5
0x1800041d1  mov     rcx, [rcx+10h]
0x1800041d5  mov     edx, 0EEh
0x1800041da  mov     r9d, eax
0x1800041dd  mov     r8, rsi
0x1800041e0  call    WPP_SF_d
0x1800041e5  mov     rcx, [rbx+50h]; hObject
0x1800041e9  call    cs:__imp_CloseHandle
0x1800041ef  mov     rcx, [rbx+10h]
0x1800041f3  mov     eax, [rbx+24h]
0x1800041f6  sub     [rcx], eax
0x1800041f8  mov     rcx, [rbx+10h]; hMem
0x1800041fc  cmp     [rcx], r15d
0x1800041ff  jnz     short loc_180004207
0x180004201  call    cs:__imp_LocalFree
0x180004207  mov     rcx, rbx; hMem
0x18000420a  mov     [rbx+38h], r15
0x18000420e  mov     [rbx+40h], r15d
0x180004212  mov     [rbx+48h], r15
0x180004216  call    cs:__imp_LocalFree
0x18000421c  test    r14, r14
0x18000421f  jnz     loc_180004021
0x180004225  inc     ebp
0x180004227  cmp     ebp, cs:dword_180036F60
0x18000422d  jb      loc_180004008
0x180004233  mov     rcx, cs:hMem; hMem
0x18000423a  test    rcx, rcx
0x18000423d  jz      short loc_180004267
0x18000423f  call    cs:__imp_LocalUnlock
0x180004245  mov     rcx, cs:hMem; hMem
0x18000424c  call    cs:__imp_LocalFree
0x180004252  mov     cs:DavUseObject, r15
0x180004259  mov     cs:dword_180036F60, r15d
0x180004260  mov     cs:hMem, r15
0x180004267  lea     rcx, Resource; Resource
0x18000426e  call    cs:__imp_RtlReleaseResource
0x180004274  add     rsp, 68h
0x180004278  pop     r15
0x18000427a  pop     r14
0x18000427c  pop     rdi
0x18000427d  pop     rsi
0x18000427e  pop     rbp
0x18000427f  pop     rbx
0x180004280  retn
```
