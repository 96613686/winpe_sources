# mciAutoOpenDevice(ushort const *,ushort const *,ushort *,uint)

- ea: `0x18000fb24`
- end: `0x18000fce3`
- name: `?mciAutoOpenDevice@@YAIPEBG0PEAGI@Z`
- size: `447`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180010504`

## callees

- `0x180003a2c`
- `0x18000f9d8`
- `0x18000fa8c`
- `0x18000fb24`
- `0x180010230`
- `0x180010c10`
- `0x180011020`
- `0x180015260`
- `0x18001a408`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fcc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fcc0`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x18000fc7d`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x18000fc7d`

## pseudocode

```c
__int64 __fastcall mciAutoOpenDevice(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  unsigned __int64 v4; // r15
  __int64 v9; // rax
  unsigned __int64 v10; // rdi
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rbx
  unsigned int v13; // edi
  unsigned __int16 *v14; // rbx
  MCIDEVICEID DeviceIDW; // eax
  unsigned int v16; // eax

  v4 = a4;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      53,
      (unsigned int)WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids,
      (_DWORD)a1,
      (__int64)a2);
  }
  if ( GetCurrentThreadId() == mciWindowThreadId )
    return 4278190080LL;
  if ( (unsigned int)mciFindNotify(a2) )
    return 300;
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  v10 = 2 * v9 + 12;
  v11 = (unsigned __int16 *)winmmAlloc((unsigned int)(2 * v9 + 12));
  v12 = v11;
  if ( !v11 )
    return 264;
  if ( StringCbPrintfW(v11, v10, szCmdFormat, wszOpen, a1) )
  {
    HeapFree(hHeap, 0, v12);
    return 261;
  }
  else
  {
    v13 = mciSendSystemString(v12, 0, 0, 0);
    HeapFree(hHeap, 0, v12);
    if ( !v13 )
    {
      v14 = 0;
      if ( a3 )
      {
        v14 = (unsigned __int16 *)winmmAlloc((unsigned int)(2 * v4 + 2));
        if ( !v14 )
        {
          DeviceIDW = mciGetDeviceIDW(a1);
          PostMessageW(hwndNotify, 0x3B9u, 0, DeviceIDW);
          return 264;
        }
      }
      v16 = mciSendSystemString(a2, 1, v14, v4);
      v13 = v16;
      if ( a3 )
      {
        if ( !v16 )
          StringCchCopyW(a3, v4, v14);
        HeapFree(hHeap, 0, v14);
      }
      if ( v13 )
        mciAutoCloseDevice(a1);
    }
    return v13;
  }
}

```

## disassembly

```asm
0x18000fb24  push    rbx
0x18000fb26  push    rbp
0x18000fb27  push    rsi
0x18000fb28  push    rdi
0x18000fb29  push    r12
0x18000fb2b  push    r14
0x18000fb2d  push    r15
0x18000fb2f  sub     rsp, 30h
0x18000fb33  mov     r15d, r9d
0x18000fb36  mov     r14, r8
0x18000fb39  mov     rbp, rdx
0x18000fb3c  mov     rsi, rcx
0x18000fb3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb46  lea     rax, WPP_GLOBAL_Control
0x18000fb4d  cmp     rcx, rax
0x18000fb50  jz      short loc_18000FB7E
0x18000fb52  test    dword ptr [rcx+1Ch], 400000h
0x18000fb59  jz      short loc_18000FB7E
0x18000fb5b  cmp     byte ptr [rcx+19h], 5
0x18000fb5f  jb      short loc_18000FB7E
0x18000fb61  mov     rcx, [rcx+10h]
0x18000fb65  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x18000fb6c  mov     edx, 35h ; '5'
0x18000fb71  mov     [rsp+68h+var_48], rbp
0x18000fb76  mov     r9, rsi
0x18000fb79  call    WPP_SF_SS
0x18000fb7e  call    cs:__imp_GetCurrentThreadId
0x18000fb84  cmp     eax, cs:?mciWindowThreadId@@3KA; ulong mciWindowThreadId
0x18000fb8a  jnz     short loc_18000FB96
0x18000fb8c  mov     eax, 0FF000000h
0x18000fb91  jmp     loc_18000FCD4
0x18000fb96  mov     rcx, rbp; unsigned __int16 *
0x18000fb99  call    ?mciFindNotify@@YAHPEBG@Z; mciFindNotify(ushort const *)
0x18000fb9e  xor     r12d, r12d
0x18000fba1  test    eax, eax
0x18000fba3  jz      short loc_18000FBAF
0x18000fba5  mov     eax, 12Ch
0x18000fbaa  jmp     loc_18000FCD4
0x18000fbaf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fbb3  inc     rax
0x18000fbb6  cmp     [rsi+rax*2], r12w
0x18000fbbb  jnz     short loc_18000FBB3
0x18000fbbd  lea     rdi, ds:0Ch[rax*2]
0x18000fbc5  mov     ecx, edi; Size
0x18000fbc7  call    winmmAlloc
0x18000fbcc  mov     rbx, rax
0x18000fbcf  test    rax, rax
0x18000fbd2  jnz     short loc_18000FBDE
0x18000fbd4  mov     eax, 108h
0x18000fbd9  jmp     loc_18000FCD4
0x18000fbde  lea     r9, ?wszOpen@@3PAGA; "open"
0x18000fbe5  mov     [rsp+68h+var_48], rsi
0x18000fbea  lea     r8, ?szCmdFormat@@3PAGA; "%ls %ls"
0x18000fbf1  mov     rdx, rdi; unsigned __int64
0x18000fbf4  mov     rcx, rbx; unsigned __int16 *
0x18000fbf7  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fbfc  xor     edx, edx; unsigned int
0x18000fbfe  test    eax, eax
0x18000fc00  jz      short loc_18000FC1C
0x18000fc02  mov     rcx, cs:hHeap; hHeap
0x18000fc09  mov     r8, rbx; lpMem
0x18000fc0c  call    cs:__imp_HeapFree
0x18000fc12  mov     eax, 105h
0x18000fc17  jmp     loc_18000FCD4
0x18000fc1c  xor     r9d, r9d; unsigned int
0x18000fc1f  xor     r8d, r8d; unsigned __int16 *
0x18000fc22  mov     rcx, rbx; unsigned __int16 *
0x18000fc25  call    ?mciSendSystemString@@YAKPEBGKPEAGI@Z; mciSendSystemString(ushort const *,ulong,ushort *,uint)
0x18000fc2a  mov     rcx, cs:hHeap; hHeap
0x18000fc31  mov     r8, rbx; lpMem
0x18000fc34  xor     edx, edx; dwFlags
0x18000fc36  mov     edi, eax
0x18000fc38  call    cs:__imp_HeapFree
0x18000fc3e  test    edi, edi
0x18000fc40  jnz     loc_18000FCD2
0x18000fc46  mov     rbx, r12
0x18000fc49  test    r14, r14
0x18000fc4c  jz      short loc_18000FC88
0x18000fc4e  lea     ecx, ds:2[r15*2]; Size
0x18000fc56  call    winmmAlloc
0x18000fc5b  mov     rbx, rax
0x18000fc5e  test    rax, rax
0x18000fc61  jnz     short loc_18000FC88
0x18000fc63  mov     rcx, rsi; pszDevice
0x18000fc66  call    mciGetDeviceIDW
0x18000fc6b  mov     rcx, cs:hwndNotify; hWnd
0x18000fc72  xor     r8d, r8d; wParam
0x18000fc75  mov     r9d, eax; lParam
0x18000fc78  mov     edx, 3B9h; Msg
0x18000fc7d  call    cs:__imp_PostMessageW
0x18000fc83  jmp     loc_18000FBD4
0x18000fc88  mov     r9d, r15d; unsigned int
0x18000fc8b  mov     r8, rbx; unsigned __int16 *
0x18000fc8e  mov     edx, 1; unsigned int
0x18000fc93  mov     rcx, rbp; unsigned __int16 *
0x18000fc96  call    ?mciSendSystemString@@YAKPEBGKPEAGI@Z; mciSendSystemString(ushort const *,ulong,ushort *,uint)
0x18000fc9b  mov     edi, eax
0x18000fc9d  test    r14, r14
0x18000fca0  jz      short loc_18000FCC6
0x18000fca2  test    eax, eax
0x18000fca4  jnz     short loc_18000FCB4
0x18000fca6  mov     rdx, r15; unsigned __int64
0x18000fca9  mov     r8, rbx; unsigned __int16 *
0x18000fcac  mov     rcx, r14; unsigned __int16 *
0x18000fcaf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fcb4  mov     rcx, cs:hHeap; hHeap
0x18000fcbb  mov     r8, rbx; lpMem
0x18000fcbe  xor     edx, edx; dwFlags
0x18000fcc0  call    cs:__imp_HeapFree
0x18000fcc6  test    edi, edi
0x18000fcc8  jz      short loc_18000FCD2
0x18000fcca  mov     rcx, rsi; unsigned __int16 *
0x18000fccd  call    ?mciAutoCloseDevice@@YAKPEBG@Z; mciAutoCloseDevice(ushort const *)
0x18000fcd2  mov     eax, edi
0x18000fcd4  add     rsp, 30h
0x18000fcd8  pop     r15
0x18000fcda  pop     r14
0x18000fcdc  pop     r12
0x18000fcde  pop     rdi
0x18000fcdf  pop     rsi
0x18000fce0  pop     rbp
0x18000fce1  pop     rbx
0x18000fce2  retn
```
