# FileStreamProp::SetSize(_ULARGE_INTEGER)

- ea: `0x18004e940`
- end: `0x18004ea45`
- name: `?SetSize@FileStreamProp@@UEAAJT_ULARGE_INTEGER@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(FileStreamProp *__hidden this, LONG lDistanceToMove)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task`

## callees

- `0x1800068f0`
- `0x18004e940`
- `0x18004eb78`
- `0x1800b0274`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e9ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ea16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e9ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ea16`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004e9bb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004e9d4`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004ea0e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004e9bb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004e9d4`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004ea0e`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18004e9e3`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18004e9e3`

## string_xrefs

- `0x18004e974`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`

## pseudocode

```c
__int64 __fastcall FileStreamProp::SetSize(HANDLE *this, __int64 lDistanceToMove)
{
  LONG v2; // ebx
  int v4; // eax
  unsigned int v5; // edi
  char *v7; // rcx
  LONG v8; // ebp
  signed int v9; // eax
  signed int LastError; // eax

  v2 = lDistanceToMove;
  if ( *((_DWORD *)this + 19) )
    Log_AssertionEvent_17(this, lDistanceToMove, 662);
  v4 = FileStreamProp::CopyOnWrite((FileStreamProp *)this);
  v5 = v4;
  if ( v4 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v4,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
      667);
    return v5;
  }
  v7 = (char *)this[1];
  if ( (unsigned __int64)(v7 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 2147500037LL;
  if ( *((_DWORD *)this + 4) )
  {
    v8 = SetFilePointer(v7, 0, 0, 1u);
    if ( v8 == -1 || SetFilePointer(this[1], v2, 0, 0) == -1 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      if ( !SetEndOfFile(this[1]) )
      {
        v9 = GetLastError();
        v5 = v9;
        if ( v9 > 0 )
          v5 = (unsigned __int16)v9 | 0x80070000;
      }
      SetFilePointer(this[1], v8, 0, 0);
    }
    *((_DWORD *)this + 9) = 1;
    return v5;
  }
  return 2147942405LL;
}

```

## disassembly

```asm
0x18004e940  push    rbx
0x18004e942  push    rbp
0x18004e943  push    rsi
0x18004e944  push    rdi
0x18004e945  sub     rsp, 38h
0x18004e949  cmp     dword ptr [rcx+4Ch], 0
0x18004e94d  mov     rbx, rdx
0x18004e950  mov     rsi, rcx
0x18004e953  jz      short loc_18004E960
0x18004e955  mov     r8d, 296h
0x18004e95b  call    Log_AssertionEvent_17
0x18004e960  mov     rcx, rsi; this
0x18004e963  call    ?CopyOnWrite@FileStreamProp@@AEAAJXZ; FileStreamProp::CopyOnWrite(void)
0x18004e968  mov     edi, eax
0x18004e96a  test    eax, eax
0x18004e96c  jns     short loc_18004E98E
0x18004e96e  mov     r9d, 29Bh
0x18004e974  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004e97b  mov     edx, 1
0x18004e980  mov     ecx, eax
0x18004e982  call    Log_UnistoreHREvent_0
0x18004e987  mov     eax, edi
0x18004e989  jmp     loc_18004EA3C
0x18004e98e  mov     rcx, [rsi+8]; hFile
0x18004e992  lea     rax, [rcx-1]
0x18004e996  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004e99a  ja      loc_18004EA37
0x18004e9a0  cmp     dword ptr [rsi+10h], 0
0x18004e9a4  jnz     short loc_18004E9B0
0x18004e9a6  mov     eax, 80070005h
0x18004e9ab  jmp     loc_18004EA3C
0x18004e9b0  mov     r9d, 1; dwMoveMethod
0x18004e9b6  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004e9b9  xor     edx, edx; lDistanceToMove
0x18004e9bb  call    cs:__imp_SetFilePointer
0x18004e9c1  mov     ebp, eax
0x18004e9c3  cmp     eax, 0FFFFFFFFh
0x18004e9c6  jz      short loc_18004EA16
0x18004e9c8  mov     rcx, [rsi+8]; hFile
0x18004e9cc  xor     r9d, r9d; dwMoveMethod
0x18004e9cf  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004e9d2  mov     edx, ebx; lDistanceToMove
0x18004e9d4  call    cs:__imp_SetFilePointer
0x18004e9da  cmp     eax, 0FFFFFFFFh
0x18004e9dd  jz      short loc_18004EA16
0x18004e9df  mov     rcx, [rsi+8]; hFile
0x18004e9e3  call    cs:__imp_SetEndOfFile
0x18004e9e9  test    eax, eax
0x18004e9eb  jnz     short loc_18004EA02
0x18004e9ed  call    cs:__imp_GetLastError
0x18004e9f3  mov     edi, eax
0x18004e9f5  test    eax, eax
0x18004e9f7  jle     short loc_18004EA02
0x18004e9f9  movzx   edi, ax
0x18004e9fc  or      edi, 80070000h
0x18004ea02  mov     rcx, [rsi+8]; hFile
0x18004ea06  xor     r9d, r9d; dwMoveMethod
0x18004ea09  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004ea0c  mov     edx, ebp; lDistanceToMove
0x18004ea0e  call    cs:__imp_SetFilePointer
0x18004ea14  jmp     short loc_18004EA2B
0x18004ea16  call    cs:__imp_GetLastError
0x18004ea1c  mov     edi, eax
0x18004ea1e  test    eax, eax
0x18004ea20  jle     short loc_18004EA2B
0x18004ea22  movzx   edi, ax
0x18004ea25  or      edi, 80070000h
0x18004ea2b  mov     dword ptr [rsi+24h], 1
0x18004ea32  jmp     loc_18004E987
0x18004ea37  mov     eax, 80004005h
0x18004ea3c  add     rsp, 38h
0x18004ea40  pop     rdi
0x18004ea41  pop     rsi
0x18004ea42  pop     rbp
0x18004ea43  pop     rbx
0x18004ea44  retn
```
