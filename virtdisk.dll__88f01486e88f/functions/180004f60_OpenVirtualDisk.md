# OpenVirtualDisk

- ea: `0x180004f60`
- end: `0x1800051ec`
- name: `OpenVirtualDisk`
- size: `652`
- prototype: `DWORD __stdcall(PVIRTUAL_STORAGE_TYPE VirtualStorageType, PCWSTR Path, VIRTUAL_DISK_ACCESS_MASK VirtualDiskAccessMask, OPEN_VIRTUAL_DISK_FLAG Flags, POPEN_VIRTUAL_DISK_PARAMETERS Parameters, PHANDLE Handle)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800085a8`

## callees

- `0x180003800`
- `0x180003930`
- `0x180004f60`
- `0x1800063a8`
- `0x180006fac`
- `0x180009890`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005096`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050d5`
- `ntdll!RtlFreeHeap` at `0x180005179`
- `ntdll!RtlFreeHeap` at `0x180005179`

## pseudocode

```c
DWORD __stdcall OpenVirtualDisk(
        PVIRTUAL_STORAGE_TYPE VirtualStorageType,
        PCWSTR Path,
        VIRTUAL_DISK_ACCESS_MASK VirtualDiskAccessMask,
        OPEN_VIRTUAL_DISK_FLAG Flags,
        POPEN_VIRTUAL_DISK_PARAMETERS Parameters,
        PHANDLE Handle)
{
  __int64 DeviceId; // r9
  _QWORD *v11; // rcx
  DWORD LastError; // ebx
  HANDLE FileW; // rax
  void *v14; // r12
  DWORD v15; // eax
  int v17; // [rsp+38h] [rbp-40h]

  if ( (Microsoft_Windows_VIRTDISKEnableBits & 1) != 0 )
  {
    DeviceId = 0;
    if ( VirtualStorageType )
      DeviceId = VirtualStorageType->DeviceId;
    McTemplateU0zq_EventWriteTransfer(VirtualStorageType, Path, Path, DeviceId);
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_8caf76d9f5ef30905b22a8ad98845768_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( VirtualStorageType )
  {
    if ( !Path )
    {
      LastError = 87;
      goto LABEL_33;
    }
    if ( (Flags & 0xFFFFE104) != 0 )
    {
      LastError = 87;
      goto LABEL_33;
    }
    if ( !Parameters || Parameters->Version == OPEN_VIRTUAL_DISK_VERSION_1 )
    {
      if ( (VirtualDiskAccessMask & 0xFFC0FFFF) != 0 )
      {
        LastError = 87;
        goto LABEL_33;
      }
    }
    else
    {
      if ( (unsigned int)(Parameters->Version - 2) > 1 )
      {
        LastError = 87;
        goto LABEL_33;
      }
      if ( VirtualDiskAccessMask )
      {
        LastError = 87;
        goto LABEL_33;
      }
    }
    FileW = CreateFileW(Path, 0x80u, 7u, 0, 3u, 0x100080u, 0);
    v14 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      LastError = GetFinalFilePathWithHandle(FileW);
      CloseHandle(v14);
    }
    if ( !LastError )
    {
      if ( (Flags & 0x1000) != 0 )
      {
        v15 = OpenVirtualDiskInternal(
                VirtualStorageType,
                0,
                (unsigned int)VirtualDiskAccessMask,
                (unsigned int)Flags,
                0,
                Parameters,
                Handle,
                0);
LABEL_31:
        LastError = v15;
        goto LABEL_32;
      }
      LastError = OpenVirtualDiskInternal(
                    VirtualStorageType,
                    0,
                    (unsigned int)VirtualDiskAccessMask,
                    (unsigned int)Flags,
                    1,
                    Parameters,
                    Handle,
                    0);
      if ( LastError == 32 )
      {
        LOBYTE(v17) = 0;
        v15 = OpenVirtualDiskInternal(
                VirtualStorageType,
                0,
                (unsigned int)VirtualDiskAccessMask,
                (unsigned int)Flags,
                0,
                Parameters,
                Handle,
                v17);
        goto LABEL_31;
      }
    }
LABEL_32:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_33;
  }
  LastError = 87;
LABEL_33:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x20) != 0 && *((_BYTE *)v11 + 25) >= 4u )
    WPP_SF_d(v11[2], 11, WPP_8caf76d9f5ef30905b22a8ad98845768_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180004f60  mov     rax, rsp
0x180004f63  push    rbx
0x180004f64  sub     rsp, 70h
0x180004f68  mov     [rax+10h], rbp
0x180004f6c  mov     rbx, rdx
0x180004f6f  mov     [rax+18h], rsi
0x180004f73  mov     ebp, r9d
0x180004f76  mov     [rax+20h], rdi
0x180004f7a  mov     rsi, rcx
0x180004f7d  mov     [rax-18h], r13
0x180004f81  xor     r13d, r13d
0x180004f84  test    cs:Microsoft_Windows_VIRTDISKEnableBits, 1
0x180004f8b  mov     edi, r13d
0x180004f8e  mov     [rax-28h], r15
0x180004f92  mov     r15d, r8d
0x180004f95  mov     [rax-38h], r13
0x180004f99  mov     [rax+8], r13d
0x180004f9d  jz      short loc_180004FB2
0x180004f9f  mov     r9d, r13d
0x180004fa2  test    rcx, rcx
0x180004fa5  jz      short loc_180004FAA
0x180004fa7  mov     r9d, [rcx]
0x180004faa  mov     r8, rbx
0x180004fad  call    McTemplateU0zq_EventWriteTransfer
0x180004fb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fb9  lea     rax, WPP_GLOBAL_Control
0x180004fc0  cmp     rcx, rax
0x180004fc3  jz      short loc_180004FED
0x180004fc5  test    byte ptr [rcx+1Ch], 20h
0x180004fc9  jz      short loc_180004FED
0x180004fcb  cmp     byte ptr [rcx+19h], 4
0x180004fcf  jb      short loc_180004FED
0x180004fd1  mov     rcx, [rcx+10h]
0x180004fd5  lea     r8, WPP_8caf76d9f5ef30905b22a8ad98845768_Traceguids
0x180004fdc  mov     edx, 0Ah
0x180004fe1  call    WPP_SF_
0x180004fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fed  test    rsi, rsi
0x180004ff0  jnz     short loc_180004FFC
0x180004ff2  mov     ebx, 57h ; 'W'
0x180004ff7  jmp     loc_180005191
0x180004ffc  test    rbx, rbx
0x180004fff  jnz     short loc_18000500B
0x180005001  mov     ebx, 57h ; 'W'
0x180005006  jmp     loc_180005191
0x18000500b  test    ebp, 0FFFFE104h
0x180005011  jz      short loc_18000501D
0x180005013  mov     ebx, 57h ; 'W'
0x180005018  jmp     loc_180005191
0x18000501d  mov     [rsp+78h+var_20], r14
0x180005022  mov     r14, [rsp+78h+Parameters]
0x18000502a  test    r14, r14
0x18000502d  jz      short loc_180005058
0x18000502f  mov     eax, [r14]
0x180005032  cmp     eax, 1
0x180005035  jz      short loc_180005058
0x180005037  add     eax, 0FFFFFFFEh
0x18000503a  cmp     eax, 1
0x18000503d  jbe     short loc_180005049
0x18000503f  mov     ebx, 57h ; 'W'
0x180005044  jmp     loc_18000518C
0x180005049  test    r15d, r15d
0x18000504c  jz      short loc_18000506B
0x18000504e  mov     ebx, 57h ; 'W'
0x180005053  jmp     loc_18000518C
0x180005058  test    r15d, 0FFC0FFFFh
0x18000505f  jz      short loc_18000506B
0x180005061  mov     ebx, 57h ; 'W'
0x180005066  jmp     loc_18000518C
0x18000506b  mov     [rsp+78h+hTemplateFile], r13; hTemplateFile
0x180005070  xor     r9d, r9d; lpSecurityAttributes
0x180005073  mov     [rsp+78h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18000507b  mov     edx, 80h; dwDesiredAccess
0x180005080  mov     r8d, 7; dwShareMode
0x180005086  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18000508e  mov     rcx, rbx; lpFileName
0x180005091  mov     [rsp+78h+var_10], r12
0x180005096  call    cs:__imp_CreateFileW
0x18000509d  nop     dword ptr [rax+rax+00h]
0x1800050a2  mov     r12, rax
0x1800050a5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800050a9  jnz     short loc_1800050BB
0x1800050ab  call    cs:__imp_GetLastError
0x1800050b2  nop     dword ptr [rax+rax+00h]
0x1800050b7  mov     ebx, eax
0x1800050b9  jmp     short loc_1800050E6
0x1800050bb  lea     r8, [rsp+78h+arg_0]
0x1800050c3  mov     rcx, r12; hFile
0x1800050c6  lea     rdx, [rsp+78h+var_38]
0x1800050cb  call    GetFinalFilePathWithHandle
0x1800050d0  mov     rcx, r12; hObject
0x1800050d3  mov     ebx, eax
0x1800050d5  call    cs:__imp_CloseHandle
0x1800050dc  nop     dword ptr [rax+rax+00h]
0x1800050e1  mov     rdi, [rsp+78h+var_38]
0x1800050e6  test    ebx, ebx
0x1800050e8  jnz     short loc_18000515D
0x1800050ea  mov     [rsp+78h+var_40], r13b
0x1800050ef  mov     r9d, ebp
0x1800050f2  mov     r8d, r15d
0x1800050f5  mov     rdx, rdi
0x1800050f8  mov     rcx, rsi
0x1800050fb  bt      ebp, 0Ch
0x1800050ff  jnb     short loc_180005110
0x180005101  mov     rax, [rsp+78h+Handle]
0x180005109  mov     [rsp+78h+hTemplateFile], rax
0x18000510e  jmp     short loc_18000514C
0x180005110  mov     r12, [rsp+78h+Handle]
0x180005118  mov     [rsp+78h+hTemplateFile], r12
0x18000511d  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r14
0x180005122  mov     [rsp+78h+dwCreationDisposition], 1
0x18000512a  call    OpenVirtualDiskInternal
0x18000512f  mov     ebx, eax
0x180005131  cmp     eax, 20h ; ' '
0x180005134  jnz     short loc_18000515D
0x180005136  mov     [rsp+78h+var_40], r13b
0x18000513b  mov     r9d, ebp
0x18000513e  mov     [rsp+78h+hTemplateFile], r12
0x180005143  mov     r8d, r15d
0x180005146  mov     rdx, rdi
0x180005149  mov     rcx, rsi
0x18000514c  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r14
0x180005151  mov     [rsp+78h+dwCreationDisposition], r13d
0x180005156  call    OpenVirtualDiskInternal
0x18000515b  mov     ebx, eax
0x18000515d  mov     r12, [rsp+78h+var_10]
0x180005162  test    rdi, rdi
0x180005165  jz      short loc_180005185
0x180005167  mov     rcx, gs:60h
0x180005170  mov     r8, rdi; P
0x180005173  xor     edx, edx; Flags
0x180005175  mov     rcx, [rcx+30h]; HeapHandle
0x180005179  call    cs:__imp_RtlFreeHeap
0x180005180  nop     dword ptr [rax+rax+00h]
0x180005185  mov     rcx, cs:WPP_GLOBAL_Control
0x18000518c  mov     r14, [rsp+78h+var_20]
0x180005191  mov     r15, [rsp+78h+var_28]
0x180005196  lea     rax, WPP_GLOBAL_Control
0x18000519d  mov     r13, [rsp+78h+var_18]
0x1800051a2  mov     rdi, [rsp+78h+arg_18]
0x1800051aa  mov     rsi, [rsp+78h+arg_10]
0x1800051b2  mov     rbp, [rsp+78h+arg_8]
0x1800051ba  cmp     rcx, rax
0x1800051bd  jz      short loc_1800051E3
0x1800051bf  test    byte ptr [rcx+1Ch], 20h
0x1800051c3  jz      short loc_1800051E3
0x1800051c5  cmp     byte ptr [rcx+19h], 4
0x1800051c9  jb      short loc_1800051E3
0x1800051cb  mov     rcx, [rcx+10h]
0x1800051cf  lea     r8, WPP_8caf76d9f5ef30905b22a8ad98845768_Traceguids
0x1800051d6  mov     edx, 0Bh
0x1800051db  mov     r9d, ebx
0x1800051de  call    WPP_SF_d
0x1800051e3  mov     eax, ebx
0x1800051e5  add     rsp, 70h
0x1800051e9  pop     rbx
0x1800051ea  retn
```
