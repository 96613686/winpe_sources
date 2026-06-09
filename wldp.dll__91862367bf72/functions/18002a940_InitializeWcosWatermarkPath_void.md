# InitializeWcosWatermarkPath(void)

- ea: `0x18002a940`
- end: `0x18002aa39`
- name: `?InitializeWcosWatermarkPath@@YAJXZ`
- size: `249`
- prototype: `signed int(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002af60`
- `0x18002b480`

## callees

- `0x180008320`
- `0x180012ef0`
- `0x180020df0`
- `0x180021ec0`
- `0x180022a10`
- `0x18002a940`
- `0x18002b670`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9fb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a9f1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a9f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int InitializeWcosWatermarkPath(void)
{
  const unsigned __int16 *v0; // r8
  __int64 v1; // rax
  int WatermarkPartitionPath; // ebx
  signed int result; // eax
  unsigned __int64 v4; // rdx
  WCHAR PathName[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(PathName, 0, 0x208u);
  v0 = qword_18005ADE0;
  if ( !qword_18005ADE0 )
    goto LABEL_5;
  v1 = -1;
  do
    ++v1;
  while ( qword_18005ADE0[v1] );
  if ( !v1 )
  {
LABEL_5:
    WatermarkPartitionPath = FindWatermarkPartitionPath((const unsigned __int16 **)&qword_18005ADE0);
    if ( WatermarkPartitionPath < 0 )
    {
      LogFormatOut("ERROR: Failed finding required partition: %S\n");
      return WatermarkPartitionPath;
    }
    v0 = qword_18005ADE0;
  }
  result = StringCchCopyW(PathName, 0x104u, v0);
  if ( result >= 0 )
  {
    result = StringCchCatW(PathName, v4, L"Microsoft");
    if ( result >= 0 )
    {
      if ( CreateDirectoryW(PathName, 0) )
        return 0;
      result = GetLastError();
      if ( result == 183 )
      {
        return 0;
      }
      else if ( result > 0 )
      {
        return (unsigned __int16)result | 0x80070000;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002a940  mov     [rsp+arg_0], rbx
0x18002a945  push    rdi
0x18002a946  sub     rsp, 240h
0x18002a94d  mov     rax, cs:__security_cookie
0x18002a954  xor     rax, rsp
0x18002a957  mov     [rsp+248h+var_18], rax
0x18002a95f  xor     edx, edx; Val
0x18002a961  lea     rcx, [rsp+248h+PathName]; void *
0x18002a966  mov     r8d, 208h; Size
0x18002a96c  call    memset_0
0x18002a971  mov     r8, cs:qword_18005ADE0
0x18002a978  xor     edi, edi
0x18002a97a  test    r8, r8
0x18002a97d  jz      short loc_18002A992
0x18002a97f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a983  inc     rax
0x18002a986  cmp     [r8+rax*2], di
0x18002a98b  jnz     short loc_18002A983
0x18002a98d  test    rax, rax
0x18002a990  jnz     short loc_18002A9C2
0x18002a992  lea     rcx, qword_18005ADE0; unsigned __int16 **
0x18002a999  call    ?FindWatermarkPartitionPath@@YAJPEAPEBG@Z; FindWatermarkPartitionPath(ushort const * *)
0x18002a99e  mov     ebx, eax
0x18002a9a0  test    eax, eax
0x18002a9a2  jns     short loc_18002A9BB
0x18002a9a4  lea     rdx, aOpp; "OPP"
0x18002a9ab  lea     rcx, aErrorFailedFin; "ERROR: Failed finding required partitio"...
0x18002a9b2  call    LogFormatOut
0x18002a9b7  mov     eax, ebx
0x18002a9b9  jmp     short loc_18002AA18
0x18002a9bb  mov     r8, cs:qword_18005ADE0; unsigned __int16 *
0x18002a9c2  mov     edx, 104h; unsigned __int64
0x18002a9c7  lea     rcx, [rsp+248h+PathName]; unsigned __int16 *
0x18002a9cc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a9d1  test    eax, eax
0x18002a9d3  js      short loc_18002AA18
0x18002a9d5  lea     r8, aMicrosoft; "Microsoft"
0x18002a9dc  lea     rcx, [rsp+248h+PathName]; unsigned __int16 *
0x18002a9e1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a9e6  test    eax, eax
0x18002a9e8  js      short loc_18002AA18
0x18002a9ea  xor     edx, edx; lpSecurityAttributes
0x18002a9ec  lea     rcx, [rsp+248h+PathName]; lpPathName
0x18002a9f1  call    cs:__imp_CreateDirectoryW
0x18002a9f7  test    eax, eax
0x18002a9f9  jnz     short loc_18002AA16
0x18002a9fb  call    cs:__imp_GetLastError
0x18002aa01  cmp     eax, 0B7h
0x18002aa06  jz      short loc_18002AA16
0x18002aa08  test    eax, eax
0x18002aa0a  jle     short loc_18002AA18
0x18002aa0c  movzx   eax, ax
0x18002aa0f  or      eax, 80070000h
0x18002aa14  jmp     short loc_18002AA18
0x18002aa16  xor     eax, eax
0x18002aa18  mov     rcx, [rsp+248h+var_18]
0x18002aa20  xor     rcx, rsp; StackCookie
0x18002aa23  call    __security_check_cookie
0x18002aa28  mov     rbx, [rsp+248h+arg_0]
0x18002aa30  add     rsp, 240h
0x18002aa37  pop     rdi
0x18002aa38  retn
```
