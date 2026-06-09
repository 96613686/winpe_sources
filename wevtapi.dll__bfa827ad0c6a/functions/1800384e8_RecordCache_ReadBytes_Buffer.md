# RecordCache::ReadBytes(Buffer &)

- ea: `0x1800384e8`
- end: `0x1800385d4`
- name: `?ReadBytes@RecordCache@@IEAAKAEAVBuffer@@@Z`
- size: `236`
- prototype: `unsigned int __fastcall(RecordCache *__hidden this, struct Buffer *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800377a8`
- `0x180037cac`
- `0x180037d98`
- `0x18003871c`
- `0x18003881c`

## callees

- `0x180009d80`
- `0x180023548`
- `0x1800373ec`
- `0x1800384e8`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038527`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180038519`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180038519`

## pseudocode

```c
__int64 __fastcall RecordCache::ReadBytes(HANDLE *this, struct Buffer *a2)
{
  DWORD v2; // r8d
  DWORD LastError; // ebx
  __int128 pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int64 v8; // [rsp+40h] [rbp-28h]
  DWORD v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+4Ch] [rbp-1Ch]
  int v11; // [rsp+50h] [rbp-18h]
  unsigned int v12; // [rsp+70h] [rbp+8h] BYREF

  v2 = *((_DWORD *)a2 + 4);
  v12 = 0;
  if ( !ReadFile(this[7], *((LPVOID *)a2 + 1), v2, &v12, 0) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, LastError);
    }
    v8 = 0;
    v9 = LastError;
    v10 = -1;
    pExceptionObject = 0;
    v11 = 358;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *((_DWORD *)a2 + 4) > v12 )
    Buffer::SetCurrentIndex(a2, v12);
  this[2] = (HANDLE)RecordCache::GetFilePosition((RecordCache *)this);
  return v12;
}

```

## disassembly

```asm
0x1800384e8  mov     rax, rsp
0x1800384eb  mov     [rax+10h], rbx
0x1800384ef  push    rdi
0x1800384f0  sub     rsp, 60h
0x1800384f4  mov     r8d, [rdx+10h]; nNumberOfBytesToRead
0x1800384f8  lea     r9, [rax+8]; lpNumberOfBytesRead
0x1800384fc  mov     rbx, rdx
0x1800384ff  mov     dword ptr [rax+8], 0
0x180038506  mov     rdx, [rdx+8]; lpBuffer
0x18003850a  mov     rdi, rcx
0x18003850d  mov     rcx, [rcx+38h]; hFile
0x180038511  mov     qword ptr [rax-48h], 0
0x180038519  call    cs:__imp_ReadFile
0x18003851f  test    eax, eax
0x180038521  jnz     loc_1800385A8
0x180038527  call    cs:__imp_GetLastError
0x18003852d  mov     ebx, eax
0x18003852f  mov     eax, 507h
0x180038534  test    ebx, ebx
0x180038536  cmovz   ebx, eax
0x180038539  mov     rcx, cs:WPP_GLOBAL_Control
0x180038540  lea     rax, WPP_GLOBAL_Control
0x180038547  cmp     rcx, rax
0x18003854a  jz      short loc_180038570
0x18003854c  test    byte ptr [rcx+1Ch], 1
0x180038550  jz      short loc_180038570
0x180038552  cmp     byte ptr [rcx+19h], 2
0x180038556  jb      short loc_180038570
0x180038558  mov     rcx, [rcx+10h]
0x18003855c  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180038563  mov     edx, 10h
0x180038568  mov     r9d, ebx
0x18003856b  call    WPP_SF_D
0x180038570  xorps   xmm0, xmm0
0x180038573  mov     [rsp+68h+var_28], 0
0x18003857c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180038583  mov     [rsp+68h+var_20], ebx
0x180038587  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18003858c  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x180038594  movdqu  [rsp+68h+pExceptionObject], xmm0
0x18003859a  mov     [rsp+68h+var_18], 166h
0x1800385a2  call    _CxxThrowException_0
0x1800385a8  mov     edx, [rsp+68h+arg_0]; unsigned int
0x1800385ac  cmp     [rbx+10h], edx
0x1800385af  jbe     short loc_1800385B9
0x1800385b1  mov     rcx, rbx; this
0x1800385b4  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x1800385b9  mov     rcx, rdi; this
0x1800385bc  call    ?GetFilePosition@RecordCache@@QEAA_KXZ; RecordCache::GetFilePosition(void)
0x1800385c1  mov     rbx, [rsp+68h+arg_8]
0x1800385c6  mov     [rdi+10h], rax
0x1800385ca  mov     eax, [rsp+68h+arg_0]
0x1800385ce  add     rsp, 60h
0x1800385d2  pop     rdi
0x1800385d3  retn
```
