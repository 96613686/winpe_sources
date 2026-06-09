# _pSpUtilsLogInitialize

- ea: `0x18001621c`
- end: `0x1800162b8`
- name: `_pSpUtilsLogInitialize`
- size: `156`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000b160`
- `0x1800177e0`

## callees

- `0x18000c180`
- `0x18001086c`
- `0x1800161d0`
- `0x18001621c`
- `0x180016424`
- `0x1800164e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001623c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800162a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001623c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800162a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016278`

## pseudocode

```c
__int64 pSpUtilsLogInitialize()
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r8
  DWORD LastError; // ebx
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+30h] [rbp-18h]

  v5 = 0;
  v6 = 0;
  if ( !dword_180023848 )
  {
    SetLastError(0x15u);
    return 0;
  }
  if ( !(unsigned int)AcquireInitMutex((signed __int64)&v5) )
    return 0;
  LastError = 0;
  if ( !g_sputils_LogInitialized )
  {
    if ( g_sputils_IsOnlineWindowsDirectory && (unsigned int)pSpUtilsSetLogPathFromRegKey(v2, v1, v3)
      || (unsigned int)pSpUtilsSetLogPath(v2, v1, v3) )
    {
      if ( (unsigned int)pSpUtilsTextLogInitialize(v2, v1, v3) )
        g_sputils_LogInitialized = 1;
      else
        LastError = 13;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  ReleaseInitMutex(&v5);
  SetLastError(LastError);
  return (unsigned int)g_sputils_LogInitialized;
}

```

## disassembly

```asm
0x18001621c  push    rbx
0x18001621e  sub     rsp, 40h
0x180016222  xor     eax, eax
0x180016224  xorps   xmm0, xmm0
0x180016227  cmp     cs:dword_180023848, eax
0x18001622d  movups  [rsp+48h+var_28], xmm0
0x180016232  mov     [rsp+48h+var_18], rax
0x180016237  jnz     short loc_180016246
0x180016239  lea     ecx, [rax+15h]; dwErrCode
0x18001623c  call    cs:__imp_SetLastError
0x180016242  xor     eax, eax
0x180016244  jmp     short loc_1800162B2
0x180016246  lea     rcx, [rsp+48h+var_28]
0x18001624b  call    _AcquireInitMutex
0x180016250  test    eax, eax
0x180016252  jz      short loc_180016242
0x180016254  xor     ebx, ebx
0x180016256  cmp     cs:g_sputils_LogInitialized, ebx
0x18001625c  jnz     short loc_18001629A
0x18001625e  cmp     cs:g_sputils_IsOnlineWindowsDirectory, ebx
0x180016264  jz      short loc_18001626F
0x180016266  call    pSpUtilsSetLogPathFromRegKey
0x18001626b  test    eax, eax
0x18001626d  jnz     short loc_180016282
0x18001626f  call    pSpUtilsSetLogPath
0x180016274  test    eax, eax
0x180016276  jnz     short loc_180016282
0x180016278  call    cs:__imp_GetLastError
0x18001627e  mov     ebx, eax
0x180016280  jmp     short loc_18001629A
0x180016282  call    _pSpUtilsTextLogInitialize
0x180016287  test    eax, eax
0x180016289  jnz     short loc_180016290
0x18001628b  lea     ebx, [rax+0Dh]
0x18001628e  jmp     short loc_18001629A
0x180016290  mov     cs:g_sputils_LogInitialized, 1
0x18001629a  lea     rcx, [rsp+48h+var_28]
0x18001629f  call    _ReleaseInitMutex
0x1800162a4  mov     ecx, ebx; dwErrCode
0x1800162a6  call    cs:__imp_SetLastError
0x1800162ac  mov     eax, cs:g_sputils_LogInitialized
0x1800162b2  add     rsp, 40h
0x1800162b6  pop     rbx
0x1800162b7  retn
```
