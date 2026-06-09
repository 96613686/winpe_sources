# mciSendCommandW

- ea: `0x180009a90`
- end: `0x180009ba7`
- name: `mciSendCommandW`
- size: `279`
- prototype: `MCIERROR __stdcall(MCIDEVICEID mciId, UINT uMsg, DWORD_PTR dwParam1, DWORD_PTR dwParam2)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011610`
- `0x180013f64`
- `0x180014b54`
- `0x18001a5f0`

## callees

- `0x180009a90`
- `0x180009bb0`
- `0x18000b1f8`
- `0x18000b42c`
- `0x180010f8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009b0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009b0c`

## pseudocode

```c
MCIERROR __stdcall mciSendCommandW(MCIDEVICEID mciId, UINT uMsg, DWORD_PTR dwParam1, DWORD_PTR dwParam2)
{
  unsigned int v9; // eax
  unsigned int v10; // ebp
  MCIERROR v11; // edi
  __int128 v13; // [rsp+30h] [rbp-48h] BYREF
  __int128 v14; // [rsp+40h] [rbp-38h]

  v13 = 0;
  v14 = 0;
  if ( !MCI_bDeviceListInitialized && !(unsigned int)mciInitDeviceList() )
    return 264;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids, uMsg, mciId);
  }
  DWORD2(v14) = 0;
  *(_QWORD *)&v14 = GetCurrentThreadId();
  v13 = 0;
  v9 = mciSendCommandInternal(mciId, uMsg, dwParam1, dwParam2, (struct MCI_INTERNAL_OPEN_INFO *)&v13);
  v10 = v9;
  v11 = (unsigned __int16)v9;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids,
      (unsigned __int16)v9);
  }
  if ( (v10 & 0x10000) != 0 )
    *(_WORD *)(dwParam2 + 10) = 0;
  if ( (unsigned __int16)v11 < 0x200u )
    return v11;
  else
    return v11 | (mciId << 16);
}

```

## disassembly

```asm
0x180009a90  push    rbx
0x180009a92  push    rbp
0x180009a93  push    rsi
0x180009a94  push    rdi
0x180009a95  push    r15
0x180009a97  sub     rsp, 50h
0x180009a9b  cmp     cs:MCI_bDeviceListInitialized, 0
0x180009aa2  xorps   xmm0, xmm0
0x180009aa5  movups  [rsp+78h+var_48], xmm0
0x180009aaa  mov     rsi, r9
0x180009aad  mov     rbp, r8
0x180009ab0  movups  [rsp+78h+var_38], xmm0
0x180009ab5  mov     edi, edx
0x180009ab7  mov     ebx, ecx
0x180009ab9  jnz     short loc_180009ACE
0x180009abb  call    mciInitDeviceList
0x180009ac0  test    eax, eax
0x180009ac2  jnz     short loc_180009ACE
0x180009ac4  mov     eax, 108h
0x180009ac9  jmp     loc_180009B9C
0x180009ace  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ad5  lea     r15, WPP_GLOBAL_Control
0x180009adc  cmp     rcx, r15
0x180009adf  jz      short loc_180009B0C
0x180009ae1  test    dword ptr [rcx+1Ch], 400000h
0x180009ae8  jz      short loc_180009B0C
0x180009aea  cmp     byte ptr [rcx+19h], 5
0x180009aee  jb      short loc_180009B0C
0x180009af0  mov     rcx, [rcx+10h]
0x180009af4  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x180009afb  mov     edx, 23h ; '#'
0x180009b00  mov     dword ptr [rsp+78h+var_58], ebx
0x180009b04  mov     r9d, edi
0x180009b07  call    WPP_SF_DD
0x180009b0c  call    cs:__imp_GetCurrentThreadId
0x180009b12  xorps   xmm0, xmm0
0x180009b15  mov     dword ptr [rsp+78h+var_38+8], 0
0x180009b1d  mov     eax, eax
0x180009b1f  mov     r9, rsi; unsigned __int64
0x180009b22  mov     qword ptr [rsp+78h+var_38], rax
0x180009b27  mov     r8, rbp; unsigned __int64
0x180009b2a  lea     rax, [rsp+78h+var_48]
0x180009b2f  mov     edx, edi; unsigned int
0x180009b31  mov     ecx, ebx; unsigned int
0x180009b33  mov     [rsp+78h+var_58], rax; struct MCI_INTERNAL_OPEN_INFO *
0x180009b38  movdqu  [rsp+78h+var_48], xmm0
0x180009b3e  call    ?mciSendCommandInternal@@YAKII_K0PEAUMCI_INTERNAL_OPEN_INFO@@@Z; mciSendCommandInternal(uint,uint,unsigned __int64,unsigned __int64,MCI_INTERNAL_OPEN_INFO *)
0x180009b43  mov     ebp, eax
0x180009b45  movzx   edi, ax
0x180009b48  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b4f  cmp     rcx, r15
0x180009b52  jz      short loc_180009B7B
0x180009b54  test    dword ptr [rcx+1Ch], 400000h
0x180009b5b  jz      short loc_180009B7B
0x180009b5d  cmp     byte ptr [rcx+19h], 5
0x180009b61  jb      short loc_180009B7B
0x180009b63  mov     rcx, [rcx+10h]
0x180009b67  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x180009b6e  mov     edx, 24h ; '$'
0x180009b73  mov     r9d, edi
0x180009b76  call    WPP_SF_d
0x180009b7b  bt      ebp, 10h
0x180009b7f  jnb     short loc_180009B87
0x180009b81  xor     eax, eax
0x180009b83  mov     [rsi+0Ah], ax
0x180009b87  mov     eax, 200h
0x180009b8c  cmp     di, ax
0x180009b8f  jb      short loc_180009B98
0x180009b91  shl     ebx, 10h
0x180009b94  or      ebx, edi
0x180009b96  jmp     short loc_180009B9A
0x180009b98  mov     ebx, edi
0x180009b9a  mov     eax, ebx
0x180009b9c  add     rsp, 50h
0x180009ba0  pop     r15
0x180009ba2  pop     rdi
0x180009ba3  pop     rsi
0x180009ba4  pop     rbp
0x180009ba5  pop     rbx
0x180009ba6  retn
```
