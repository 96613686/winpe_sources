# MtMgrOpen(void * *)

- ea: `0x1400228bc`
- end: `0x1400229db`
- name: `?MtMgrOpen@@YAHPEAPEAX@Z`
- size: `287`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path`

## callers

- `0x140021cd8`

## callees

- `0x140021ca0`
- `0x1400228bc`
- `0x1400235a8`
- `0x1400d257c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400229c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400229c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022986`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140022947`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140022947`

## string_xrefs

- `0x1400228ce`: `MtMgrOpen`
- `0x1400229b5`: `MtMgrOpen`
- `0x140022925`: `\\.\MountPointManager`
- `0x140022905`: `hMountMgrOut != NULL`

## pseudocode

```c
__int64 __fastcall MtMgrOpen(void **a1)
{
  unsigned int v2; // edi
  DWORD LastError; // ebx
  char *FileW; // rcx
  DWORD v5; // eax

  TraceFunctionEnter(L"MtMgrOpen");
  if ( a1 )
  {
    FileW = (char *)CreateFileW(L"\\\\.\\MountPointManager", 0xC0000000, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v2 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v5 = GetLastError();
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          39,
          (unsigned int)WPP_78d403bd48723deb5f738664aa5853e8_Traceguids,
          v5,
          "GetLastError()");
      }
    }
    else
    {
      LastError = 0;
      *a1 = FileW;
      v2 = 1;
    }
  }
  else
  {
    v2 = 0;
    LastError = 87;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        38,
        (unsigned int)WPP_78d403bd48723deb5f738664aa5853e8_Traceguids,
        87,
        "hMountMgrOut != NULL");
    }
  }
  TraceFunctionExit(L"MtMgrOpen");
  SetLastError(LastError);
  return v2;
}

```

## disassembly

```asm
0x1400228bc  mov     [rsp+arg_0], rbx
0x1400228c1  mov     [rsp+arg_8], rsi
0x1400228c6  push    rdi
0x1400228c7  sub     rsp, 40h
0x1400228cb  mov     rsi, rcx
0x1400228ce  lea     rcx, aMtmgropen; "MtMgrOpen"
0x1400228d5  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x1400228da  test    rsi, rsi
0x1400228dd  jnz     short loc_14002291C
0x1400228df  xor     edi, edi
0x1400228e1  lea     ebx, [rsi+57h]
0x1400228e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400228eb  lea     rax, WPP_GLOBAL_Control
0x1400228f2  cmp     rcx, rax
0x1400228f5  jz      loc_1400229B5
0x1400228fb  test    byte ptr [rcx+1Ch], 8
0x1400228ff  jz      loc_1400229B5
0x140022905  lea     rax, aHmountmgroutNu; "hMountMgrOut != NULL"
0x14002290c  mov     r9d, ebx
0x14002290f  mov     qword ptr [rsp+48h+dwCreationDisposition], rax
0x140022914  lea     edx, [rsi+26h]
0x140022917  jmp     loc_1400229A5
0x14002291c  mov     [rsp+48h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x140022925  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x14002292c  mov     r8d, 3; dwShareMode
0x140022932  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14002293a  xor     r9d, r9d; lpSecurityAttributes
0x14002293d  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x140022942  mov     edx, 0C0000000h; dwDesiredAccess
0x140022947  call    cs:__imp_CreateFileW
0x14002294d  mov     rcx, rax
0x140022950  dec     rax
0x140022953  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140022957  ja      short loc_140022963
0x140022959  xor     ebx, ebx
0x14002295b  mov     [rsi], rcx
0x14002295e  lea     edi, [rbx+1]
0x140022961  jmp     short loc_1400229B5
0x140022963  xor     edi, edi
0x140022965  call    cs:__imp_GetLastError
0x14002296b  mov     ebx, eax
0x14002296d  mov     rcx, cs:WPP_GLOBAL_Control
0x140022974  lea     rax, WPP_GLOBAL_Control
0x14002297b  cmp     rcx, rax
0x14002297e  jz      short loc_1400229B5
0x140022980  test    byte ptr [rcx+1Ch], 8
0x140022984  jz      short loc_1400229B5
0x140022986  call    cs:__imp_GetLastError
0x14002298c  mov     rcx, cs:WPP_GLOBAL_Control
0x140022993  lea     r8, aGetlasterror_1; "GetLastError()"
0x14002299a  mov     qword ptr [rsp+48h+dwCreationDisposition], r8
0x14002299f  lea     edx, [rdi+27h]
0x1400229a2  mov     r9d, eax
0x1400229a5  mov     rcx, [rcx+10h]
0x1400229a9  lea     r8, WPP_78d403bd48723deb5f738664aa5853e8_Traceguids
0x1400229b0  call    WPP_SF_Ds
0x1400229b5  lea     rcx, aMtmgropen; "MtMgrOpen"
0x1400229bc  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x1400229c1  mov     ecx, ebx; dwErrCode
0x1400229c3  call    cs:__imp_SetLastError
0x1400229c9  mov     rbx, [rsp+48h+arg_0]
0x1400229ce  mov     eax, edi
0x1400229d0  mov     rsi, [rsp+48h+arg_8]
0x1400229d5  add     rsp, 40h
0x1400229d9  pop     rdi
0x1400229da  retn
```
