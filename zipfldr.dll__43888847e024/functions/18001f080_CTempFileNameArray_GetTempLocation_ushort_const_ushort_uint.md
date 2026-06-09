# CTempFileNameArray::GetTempLocation(ushort const *,ushort *,uint)

- ea: `0x18001f080`
- end: `0x18001f134`
- name: `?GetTempLocation@CTempFileNameArray@@QEAAJPEBGPEAGI@Z`
- size: `180`
- prototype: `__int64 __fastcall(CTempFileNameArray *this, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e970`
- `0x18001ea30`
- `0x180026600`
- `0x180043de8`
- `0x18004666c`
- `0x180047670`
- `0x180059000`

## callees

- `0x18001f080`
- `0x18001fe64`
- `0x1800350a0`
- `0x180036f50`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18001f0e0`
- `SHLWAPI!PathFindFileNameW` at `0x18001f0e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f104`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f104`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f0b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f0b8`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001f0c8`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001f0c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CTempFileNameArray::GetTempLocation(
        CTempFileNameArray *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  CTempFileNameArray *v3; // rbp
  int Error; // ebx
  const unsigned __int16 *FileNameW; // rax
  unsigned int v9; // [rsp+28h] [rbp-240h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-238h] BYREF

  v3 = g_pCTFA;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pCTFA + 8));
  if ( GetTempPathW(0x104u, Buffer) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    FileNameW = PathFindFileNameW(a2);
    Error = CTempFileNameArray::_TryCreatingInPath(v3, a2, Buffer, FileNameW, a3, v9);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 8));
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001f080  mov     [rsp+arg_0], rbx
0x18001f085  mov     [rsp+arg_18], rbp
0x18001f08a  push    rsi
0x18001f08b  push    rdi
0x18001f08c  push    r14
0x18001f08e  sub     rsp, 250h
0x18001f095  mov     rax, cs:__security_cookie
0x18001f09c  xor     rax, rsp
0x18001f09f  mov     [rsp+268h+var_28], rax
0x18001f0a7  mov     rbp, cs:?g_pCTFA@@3PEAVCTempFileNameArray@@EA; CTempFileNameArray * g_pCTFA
0x18001f0ae  mov     r14, r8
0x18001f0b1  mov     rsi, rdx
0x18001f0b4  lea     rcx, [rbp+8]; lpCriticalSection
0x18001f0b8  call    cs:__imp_EnterCriticalSection
0x18001f0be  lea     rdx, [rsp+268h+Buffer]; lpBuffer
0x18001f0c3  mov     ecx, 104h; nBufferLength
0x18001f0c8  call    cs:__imp_GetTempPathW
0x18001f0ce  test    eax, eax
0x18001f0d0  jnz     short loc_18001F0DD
0x18001f0d2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001f0d7  mov     ebx, eax
0x18001f0d9  test    eax, eax
0x18001f0db  js      short loc_18001F100
0x18001f0dd  mov     rcx, rsi; pszPath
0x18001f0e0  call    cs:__imp_PathFindFileNameW
0x18001f0e6  lea     r8, [rsp+268h+Buffer]; unsigned __int16 *
0x18001f0eb  mov     [rsp+268h+var_248], r14; unsigned __int16 *
0x18001f0f0  mov     r9, rax; unsigned __int16 *
0x18001f0f3  mov     rdx, rsi; unsigned __int16 *
0x18001f0f6  mov     rcx, rbp; this
0x18001f0f9  call    ?_TryCreatingInPath@CTempFileNameArray@@AEAAJPEBG00PEAGI@Z; CTempFileNameArray::_TryCreatingInPath(ushort const *,ushort const *,ushort const *,ushort *,uint)
0x18001f0fe  mov     ebx, eax
0x18001f100  lea     rcx, [rbp+8]; lpCriticalSection
0x18001f104  call    cs:__imp_LeaveCriticalSection
0x18001f10a  mov     eax, ebx
0x18001f10c  mov     rcx, [rsp+268h+var_28]
0x18001f114  xor     rcx, rsp; StackCookie
0x18001f117  call    __security_check_cookie
0x18001f11c  lea     r11, [rsp+268h+var_18]
0x18001f124  mov     rbx, [r11+20h]
0x18001f128  mov     rbp, [r11+38h]
0x18001f12c  mov     rsp, r11
0x18001f12f  pop     r14
0x18001f131  pop     rdi
0x18001f132  pop     rsi
0x18001f133  retn
```
