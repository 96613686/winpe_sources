# AuthPortMgrValidateAndRefPort

- ea: `0x18007c42c`
- end: `0x18007c56d`
- name: `AuthPortMgrValidateAndRefPort`
- size: `321`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180079e50`
- `0x18007a4f4`
- `0x18007ab80`
- `0x18007ace0`
- `0x18007ae60`
- `0x18007afc0`
- `0x18007c968`
- `0x18007d200`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18007c42c`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18007c4f4`
- `MobileNetworking!ReleaseWriteLock` at `0x18007c4f4`
- `MobileNetworking!AcquireWriteLock` at `0x18007c4a5`
- `MobileNetworking!AcquireWriteLock` at `0x18007c4a5`

## pseudocode

```c
__int64 __fastcall AuthPortMgrValidateAndRefPort(__int64 a1, _DWORD *a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  int v6; // ebp
  __int64 i; // rax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 && a2 )
  {
    v5 = 0;
    v6 = 0;
    *a2 = 0;
    AcquireWriteLock(&g_WcnOneXInfo, qword_1800BB520, "AuthPortMgrValidateAndRefPort", 333);
    for ( i = qword_1800BB510; (__int64 *)i != &qword_1800BB510; i = *(_QWORD *)i )
    {
      if ( a1 == i )
      {
        v6 = 1;
        _InterlockedIncrement((volatile signed __int32 *)(i + 16));
        *a2 = 1;
        break;
      }
    }
    ReleaseWriteLock(&g_WcnOneXInfo, qword_1800BB520, "AuthPortMgrValidateAndRefPort", 352);
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( !v6 )
      v5 = 1168;
  }
  else
  {
    v5 = 6;
    if ( v4 == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)v4 + 28) & 2) != 0 )
    {
      WPP_SF_(v4[2], 34, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
    WPP_SF_d(v4[2], 35, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18007c42c  push    rbx
0x18007c42e  push    rbp
0x18007c42f  push    rsi
0x18007c430  push    rdi
0x18007c431  push    r15
0x18007c433  sub     rsp, 20h
0x18007c437  mov     rdi, rdx
0x18007c43a  mov     rsi, rcx
0x18007c43d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c444  lea     r15, WPP_GLOBAL_Control
0x18007c44b  cmp     rcx, r15
0x18007c44e  jz      short loc_18007C472
0x18007c450  test    byte ptr [rcx+1Ch], 1
0x18007c454  jz      short loc_18007C472
0x18007c456  mov     rcx, [rcx+10h]
0x18007c45a  lea     r8, WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids
0x18007c461  mov     edx, 21h ; '!'
0x18007c466  call    WPP_SF_
0x18007c46b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c472  test    rsi, rsi
0x18007c475  jz      loc_18007C512
0x18007c47b  test    rdi, rdi
0x18007c47e  jz      loc_18007C512
0x18007c484  xor     ebx, ebx
0x18007c486  lea     r8, aAuthportmgrval; "AuthPortMgrValidateAndRefPort"
0x18007c48d  xor     ebp, ebp
0x18007c48f  mov     [rdi], ebx
0x18007c491  mov     r9d, 14Dh
0x18007c497  lea     rdx, qword_1800BB520
0x18007c49e  lea     rcx, g_WcnOneXInfo
0x18007c4a5  call    cs:__imp_AcquireWriteLock
0x18007c4ac  nop     dword ptr [rax+rax+00h]
0x18007c4b1  mov     rax, cs:qword_1800BB510
0x18007c4b8  lea     rcx, qword_1800BB510
0x18007c4bf  cmp     rax, rcx
0x18007c4c2  jz      short loc_18007C4D9
0x18007c4c4  cmp     rsi, rax
0x18007c4c7  jz      short loc_18007C4CE
0x18007c4c9  mov     rax, [rax]
0x18007c4cc  jmp     short loc_18007C4B8
0x18007c4ce  mov     ebp, 1
0x18007c4d3  lock inc dword ptr [rax+10h]
0x18007c4d7  mov     [rdi], ebp
0x18007c4d9  mov     r9d, 160h
0x18007c4df  lea     r8, aAuthportmgrval; "AuthPortMgrValidateAndRefPort"
0x18007c4e6  lea     rdx, qword_1800BB520
0x18007c4ed  lea     rcx, g_WcnOneXInfo
0x18007c4f4  call    cs:__imp_ReleaseWriteLock
0x18007c4fb  nop     dword ptr [rax+rax+00h]
0x18007c500  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c507  test    ebp, ebp
0x18007c509  jnz     short loc_18007C53C
0x18007c50b  mov     ebx, 490h
0x18007c510  jmp     short loc_18007C53C
0x18007c512  mov     ebx, 6
0x18007c517  cmp     rcx, r15
0x18007c51a  jz      short loc_18007C55F
0x18007c51c  test    byte ptr [rcx+1Ch], 2
0x18007c520  jz      short loc_18007C53C
0x18007c522  mov     rcx, [rcx+10h]
0x18007c526  lea     edx, [rbx+1Ch]
0x18007c529  lea     r8, WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids
0x18007c530  call    WPP_SF_
0x18007c535  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c53c  cmp     rcx, r15
0x18007c53f  jz      short loc_18007C55F
0x18007c541  test    byte ptr [rcx+1Ch], 1
0x18007c545  jz      short loc_18007C55F
0x18007c547  mov     rcx, [rcx+10h]
0x18007c54b  lea     r8, WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids
0x18007c552  mov     edx, 23h ; '#'
0x18007c557  mov     r9d, ebx
0x18007c55a  call    WPP_SF_d
0x18007c55f  mov     eax, ebx
0x18007c561  add     rsp, 20h
0x18007c565  pop     r15
0x18007c567  pop     rdi
0x18007c568  pop     rsi
0x18007c569  pop     rbp
0x18007c56a  pop     rbx
0x18007c56b  retn
```
