# WerpRefreshRootPath

- ea: `0x14000f8bc`
- end: `0x14000fb98`
- name: `WerpRefreshRootPath`
- size: `732`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14000e194`

## callees

- `0x140002820`
- `0x140002940`
- `0x14000d174`
- `0x14000eb08`
- `0x14000f3e0`
- `0x14000f640`
- `0x14000f8bc`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000f9e6`
- `ntoskrnl!DbgPrintEx` at `0x14000fa16`
- `ntoskrnl!DbgPrintEx` at `0x14000fb0f`
- `ntoskrnl!DbgPrintEx` at `0x14000f9e6`
- `ntoskrnl!DbgPrintEx` at `0x14000fa16`
- `ntoskrnl!DbgPrintEx` at `0x14000fb0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fb46`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fb5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fb46`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fb5c`
- `ntoskrnl!ZwClose` at `0x14000fb71`
- `ntoskrnl!ZwClose` at `0x14000fb71`

## string_xrefs

- `0x14000f8da`: `LiveKernelReportsPath`
- `0x14000f925`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl\LiveKernelReports`
- `0x14000f9d8`: `WERKERNELHOST: WerpRefreshRootPath: LiveKernelReportsPath value is an invalid string.\n`
- `0x14000fa08`: `WERKERNELHOST: The live reports root path has changed.\n`
- `0x14000faa6`: `WERKERNELHOST: New root path buffer could not be allocated. Using existing path.\n`
- `0x14000fb03`: `WERKERNELHOST: Could not create new root path. Using existing path.\n`

## pseudocode

```c
__int64 WerpRefreshRootPath()
{
  bool v1; // r14
  int RegistryKey; // esi
  char v3; // di
  char v4; // r12
  __int64 v5; // rdx
  WCHAR *Buffer; // r15
  USHORT Length; // r13
  struct _UNICODE_STRING ValueName; // [rsp+20h] [rbp-10h] BYREF
  bool v9; // [rsp+70h] [rbp+40h]
  USHORT P; // [rsp+78h] [rbp+48h]
  HANDLE Handle; // [rsp+80h] [rbp+50h] BYREF

  ValueName.Buffer = L"LiveKernelReportsPath";
  *(_QWORD *)&ValueName.Length = 2883626;
  if ( !WerKernelLiveReportInitialized )
    return 3221225473LL;
  Handle = 0;
  v1 = WerKernelLiveReportRootPath.Buffer == L"\\SystemRoot\\LiveKernelReports";
  v9 = WerKernelLiveReportRootPath.Buffer == L"\\SystemRoot\\LiveKernelReports";
  RegistryKey = WerpGetRegistryKey(
                  0,
                  L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl\\LiveKernelReports",
                  0x20000,
                  &Handle);
  if ( RegistryKey >= 0 )
  {
    RegistryKey = WerpGetRegistryValueInfo(Handle, &ValueName);
    v3 = 1;
    if ( RegistryKey < 0 )
    {
      v4 = 0;
      if ( !v1 )
        goto LABEL_13;
    }
    else
    {
      if ( MEMORY[4] == 1
        && (MEMORY[8] & 1) == 0
        && (unsigned int)(MEMORY[8] - 1) <= 0x205
        && !*(_WORD *)(MEMORY[8] + 0xALL) )
      {
        v4 = 1;
LABEL_13:
        DbgPrintEx(5u, 3u, "WERKERNELHOST: The live reports root path has changed.\n");
        Buffer = WerKernelLiveReportRootPath.Buffer;
        Length = WerKernelLiveReportRootPath.Length;
        P = WerKernelLiveReportRootPath.MaximumLength;
        if ( v9 )
        {
          WerKernelLiveReportRootPath.Buffer = 0;
          v3 = 0;
          *(_DWORD *)&WerKernelLiveReportRootPath.Length = 0;
          if ( !v4 )
            goto LABEL_22;
        }
        else
        {
          if ( !v4 )
          {
            *(_DWORD *)&WerKernelLiveReportRootPath.Length = 3932218;
            WerKernelLiveReportRootPath.Buffer = L"\\SystemRoot\\LiveKernelReports";
            goto LABEL_22;
          }
          WerKernelLiveReportRootPath.Buffer = 0;
          *(_DWORD *)&WerKernelLiveReportRootPath.Length = 0;
        }
        WerKernelLiveReportRootPath.Buffer = (PWSTR)WerpAllocateMem(MEMORY[8], v5);
        if ( !WerKernelLiveReportRootPath.Buffer )
        {
          WerKernelLiveReportRootPath.MaximumLength = P;
          RegistryKey = -1073741801;
          WerKernelLiveReportRootPath.Buffer = Buffer;
          WerKernelLiveReportRootPath.Length = Length;
          DbgPrintEx(5u, 0, "WERKERNELHOST: New root path buffer could not be allocated. Using existing path.\n");
          goto LABEL_27;
        }
        WerKernelLiveReportRootPath.MaximumLength = MEMORY[8];
        WerKernelLiveReportRootPath.Length = MEMORY[8] - 2;
        memmove(WerKernelLiveReportRootPath.Buffer, (const void *)0xC, (unsigned __int16)(MEMORY[8] - 2));
LABEL_22:
        RegistryKey = WerpCreateStoreDirectory();
        if ( RegistryKey >= 0 )
        {
          if ( v3 && Buffer )
            ExFreePoolWithTag(Buffer, 0);
        }
        else
        {
          DbgPrintEx(5u, 0, "WERKERNELHOST: Could not create new root path. Using existing path.\n");
          WerKernelLiveReportRootPath.MaximumLength = P;
          WerKernelLiveReportRootPath.Buffer = Buffer;
          WerKernelLiveReportRootPath.Length = Length;
        }
        goto LABEL_27;
      }
      DbgPrintEx(5u, 0, "WERKERNELHOST: WerpRefreshRootPath: LiveKernelReportsPath value is an invalid string.\n");
    }
  }
LABEL_27:
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)RegistryKey;
}

```

## disassembly

```asm
0x14000f8bc  mov     [rsp-38h+arg_18], rbx
0x14000f8c1  push    rbp
0x14000f8c2  push    rsi
0x14000f8c3  push    rdi
0x14000f8c4  push    r12
0x14000f8c6  push    r13
0x14000f8c8  push    r14
0x14000f8ca  push    r15
0x14000f8cc  mov     rbp, rsp
0x14000f8cf  sub     rsp, 30h
0x14000f8d3  cmp     cs:WerKernelLiveReportInitialized, 0
0x14000f8da  lea     rax, aLivekernelrepo_1; "LiveKernelReportsPath"
0x14000f8e1  mov     [rbp+ValueName.Buffer], rax
0x14000f8e5  mov     qword ptr [rbp+ValueName.Length], 2C002Ah
0x14000f8ed  jnz     short loc_14000F8F9
0x14000f8ef  mov     eax, 0C0000001h
0x14000f8f4  jmp     loc_14000FB7F
0x14000f8f9  lea     rax, aSystemrootLive; "\\SystemRoot\\LiveKernelReports"
0x14000f900  mov     [rbp+P], 0
0x14000f908  cmp     cs:WerKernelLiveReportRootPath.Buffer, rax
0x14000f90f  lea     r9, [rbp+Handle]
0x14000f913  mov     r8d, 20000h
0x14000f919  mov     [rbp+Handle], 0
0x14000f921  setz    r14b
0x14000f925  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000f92c  xor     ecx, ecx
0x14000f92e  mov     [rbp+arg_0], r14b
0x14000f932  call    WerpGetRegistryKey
0x14000f937  mov     esi, eax
0x14000f939  test    eax, eax
0x14000f93b  js      loc_14000FB68
0x14000f941  mov     rcx, [rbp+Handle]; KeyHandle
0x14000f945  lea     r8, [rbp+P]
0x14000f949  lea     rdx, [rbp+ValueName]; ValueName
0x14000f94d  call    WerpGetRegistryValueInfo
0x14000f952  mov     rbx, [rbp+P]
0x14000f956  mov     esi, eax
0x14000f958  mov     edi, 1
0x14000f95d  test    eax, eax
0x14000f95f  js      loc_14000F9F7
0x14000f965  cmp     [rbx+4], edi
0x14000f968  jnz     short loc_14000F9D8
0x14000f96a  mov     ecx, [rbx+8]
0x14000f96d  mov     eax, ecx
0x14000f96f  and     eax, edi
0x14000f971  test    al, al
0x14000f973  jnz     short loc_14000F9D8
0x14000f975  lea     eax, [rcx-1]
0x14000f978  cmp     eax, 205h
0x14000f97d  ja      short loc_14000F9D8
0x14000f97f  xor     eax, eax
0x14000f981  cmp     ax, [rcx+rbx+0Ah]
0x14000f986  jnz     short loc_14000F9D8
0x14000f988  mov     r9, cs:WerKernelLiveReportRootPath.Buffer
0x14000f98f  test    r9, r9
0x14000f992  jz      short loc_14000F9C8
0x14000f994  test    rbx, rbx
0x14000f997  jz      short loc_14000F9C8
0x14000f999  cmp     [rbx+4], edi
0x14000f99c  jnz     short loc_14000F9C8
0x14000f99e  movzx   eax, cs:WerKernelLiveReportRootPath.Length
0x14000f9a5  movzx   ecx, word ptr [rbx+8]
0x14000f9a9  mov     r8d, eax; Size
0x14000f9ac  add     rax, 2
0x14000f9b0  cmp     rax, rcx
0x14000f9b3  jnz     short loc_14000F9C8
0x14000f9b5  lea     rdx, [rbx+0Ch]; Buf2
0x14000f9b9  mov     rcx, r9; Buf1
0x14000f9bc  call    memcmp
0x14000f9c1  test    eax, eax
0x14000f9c3  setnz   al
0x14000f9c6  jmp     short loc_14000F9CB
0x14000f9c8  mov     al, dil
0x14000f9cb  mov     r12b, dil
0x14000f9ce  test    al, al
0x14000f9d0  jz      loc_14000FB52
0x14000f9d6  jmp     short loc_14000FA03
0x14000f9d8  lea     r8, aWerkernelhostW_43; "WERKERNELHOST: WerpRefreshRootPath: Liv"...
0x14000f9df  mov     ecx, 5; ComponentId
0x14000f9e4  xor     edx, edx; Level
0x14000f9e6  call    cs:__imp_DbgPrintEx
0x14000f9ed  nop     dword ptr [rax+rax+00h]
0x14000f9f2  jmp     loc_14000FB52
0x14000f9f7  xor     r12b, r12b
0x14000f9fa  test    r14b, r14b
0x14000f9fd  jnz     loc_14000FB52
0x14000fa03  mov     edx, 3; Level
0x14000fa08  lea     r8, aWerkernelhostT; "WERKERNELHOST: The live reports root pa"...
0x14000fa0f  lea     r14d, [rdx+2]
0x14000fa13  mov     ecx, r14d; ComponentId
0x14000fa16  call    cs:__imp_DbgPrintEx
0x14000fa1d  nop     dword ptr [rax+rax+00h]
0x14000fa22  movzx   eax, cs:WerKernelLiveReportRootPath.MaximumLength
0x14000fa29  xor     esi, esi
0x14000fa2b  mov     r15, cs:WerKernelLiveReportRootPath.Buffer
0x14000fa32  movzx   r13d, cs:WerKernelLiveReportRootPath.Length
0x14000fa3a  mov     word ptr [rbp+P], ax
0x14000fa3e  cmp     [rbp+arg_0], sil
0x14000fa42  jz      short loc_14000FA5F
0x14000fa44  mov     cs:WerKernelLiveReportRootPath.Buffer, rsi
0x14000fa4b  mov     dil, sil
0x14000fa4e  mov     dword ptr cs:WerKernelLiveReportRootPath.Length, esi
0x14000fa54  test    r12b, r12b
0x14000fa57  jz      loc_14000FAF8
0x14000fa5d  jmp     short loc_14000FA8B
0x14000fa5f  test    r12b, r12b
0x14000fa62  jnz     short loc_14000FA7E
0x14000fa64  lea     rax, aSystemrootLive; "\\SystemRoot\\LiveKernelReports"
0x14000fa6b  mov     dword ptr cs:WerKernelLiveReportRootPath.Length, 3C003Ah
0x14000fa75  mov     cs:WerKernelLiveReportRootPath.Buffer, rax
0x14000fa7c  jmp     short loc_14000FAF8
0x14000fa7e  mov     cs:WerKernelLiveReportRootPath.Buffer, rsi
0x14000fa85  mov     dword ptr cs:WerKernelLiveReportRootPath.Length, esi
0x14000fa8b  mov     ecx, [rbx+8]
0x14000fa8e  call    WerpAllocateMem
0x14000fa93  mov     cs:WerKernelLiveReportRootPath.Buffer, rax
0x14000fa9a  mov     rcx, rax; void *
0x14000fa9d  test    rax, rax
0x14000faa0  jnz     short loc_14000FAD0
0x14000faa2  movzx   eax, word ptr [rbp+P]
0x14000faa6  lea     r8, aWerkernelhostN_0; "WERKERNELHOST: New root path buffer cou"...
0x14000faad  mov     cs:WerKernelLiveReportRootPath.MaximumLength, ax
0x14000fab4  mov     esi, 0C0000017h
0x14000fab9  mov     cs:WerKernelLiveReportRootPath.Buffer, r15
0x14000fac0  mov     ecx, r14d
0x14000fac3  mov     cs:WerKernelLiveReportRootPath.Length, r13w
0x14000facb  jmp     loc_14000F9E4
0x14000fad0  movzx   eax, word ptr [rbx+8]
0x14000fad4  lea     rdx, [rbx+0Ch]; Src
0x14000fad8  mov     cs:WerKernelLiveReportRootPath.MaximumLength, ax
0x14000fadf  movzx   eax, word ptr [rbx+8]
0x14000fae3  sub     ax, 2
0x14000fae7  movzx   r8d, ax; Size
0x14000faeb  mov     cs:WerKernelLiveReportRootPath.Length, r8w
0x14000faf3  call    memmove
0x14000faf8  call    WerpCreateStoreDirectory
0x14000fafd  mov     esi, eax
0x14000faff  test    eax, eax
0x14000fb01  jns     short loc_14000FB37
0x14000fb03  lea     r8, aWerkernelhostC; "WERKERNELHOST: Could not create new roo"...
0x14000fb0a  xor     edx, edx; Level
0x14000fb0c  mov     ecx, r14d; ComponentId
0x14000fb0f  call    cs:__imp_DbgPrintEx
0x14000fb16  nop     dword ptr [rax+rax+00h]
0x14000fb1b  movzx   eax, word ptr [rbp+P]
0x14000fb1f  mov     cs:WerKernelLiveReportRootPath.MaximumLength, ax
0x14000fb26  mov     cs:WerKernelLiveReportRootPath.Buffer, r15
0x14000fb2d  mov     cs:WerKernelLiveReportRootPath.Length, r13w
0x14000fb35  jmp     short loc_14000FB52
0x14000fb37  test    dil, dil
0x14000fb3a  jz      short loc_14000FB52
0x14000fb3c  test    r15, r15
0x14000fb3f  jz      short loc_14000FB52
0x14000fb41  xor     edx, edx; Tag
0x14000fb43  mov     rcx, r15; P
0x14000fb46  call    cs:__imp_ExFreePoolWithTag
0x14000fb4d  nop     dword ptr [rax+rax+00h]
0x14000fb52  test    rbx, rbx
0x14000fb55  jz      short loc_14000FB68
0x14000fb57  xor     edx, edx; Tag
0x14000fb59  mov     rcx, rbx; P
0x14000fb5c  call    cs:__imp_ExFreePoolWithTag
0x14000fb63  nop     dword ptr [rax+rax+00h]
0x14000fb68  mov     rcx, [rbp+Handle]; Handle
0x14000fb6c  test    rcx, rcx
0x14000fb6f  jz      short loc_14000FB7D
0x14000fb71  call    cs:__imp_ZwClose
0x14000fb78  nop     dword ptr [rax+rax+00h]
0x14000fb7d  mov     eax, esi
0x14000fb7f  mov     rbx, [rsp+30h+arg_18]
0x14000fb87  add     rsp, 30h
0x14000fb8b  pop     r15
0x14000fb8d  pop     r14
0x14000fb8f  pop     r13
0x14000fb91  pop     r12
0x14000fb93  pop     rdi
0x14000fb94  pop     rsi
0x14000fb95  pop     rbp
0x14000fb96  retn
```
