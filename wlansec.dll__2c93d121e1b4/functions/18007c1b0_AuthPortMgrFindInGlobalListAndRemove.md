# AuthPortMgrFindInGlobalListAndRemove

- ea: `0x18007c1b0`
- end: `0x18007c300`
- name: `AuthPortMgrFindInGlobalListAndRemove`
- size: `336`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180042ec0`
- `0x18007c088`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18007c1b0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18007c2ab`
- `MobileNetworking!ReleaseWriteLock` at `0x18007c2ab`
- `MobileNetworking!AcquireWriteLock` at `0x18007c245`
- `MobileNetworking!AcquireWriteLock` at `0x18007c245`

## string_xrefs

- `0x18007c22a`: `AuthPortMgrFindInGlobalListAndRemove`
- `0x18007c296`: `AuthPortMgrFindInGlobalListAndRemove`

## pseudocode

```c
__int64 __fastcall AuthPortMgrFindInGlobalListAndRemove(__int64 *a1, int a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  int v6; // edi
  __int64 *i; // rax
  __int64 v8; // rcx
  __int64 **v9; // rdx

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v6 = 0;
    AcquireWriteLock(&g_WcnOneXInfo, qword_1800BB520, "AuthPortMgrFindInGlobalListAndRemove", 237);
    for ( i = (__int64 *)qword_1800BB510; i != &qword_1800BB510; i = (__int64 *)*i )
    {
      if ( a1 == i )
      {
        if ( a2 )
        {
          v8 = *i;
          if ( *(__int64 **)(*i + 8) != i || (v9 = (__int64 **)i[1], *v9 != i) )
            __fastfail(3u);
          *v9 = (__int64 *)v8;
          *(_QWORD *)(v8 + 8) = v9;
        }
        v6 = 1;
        break;
      }
    }
    ReleaseWriteLock(&g_WcnOneXInfo, qword_1800BB520, "AuthPortMgrFindInGlobalListAndRemove", 258);
    v5 = v6 == 0 ? 0x490 : 0;
    goto LABEL_18;
  }
  v5 = 6;
  if ( v4 == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v4 + 28) & 2) != 0 )
  {
    WPP_SF_(v4[2], 29, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids);
LABEL_18:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
    WPP_SF_d(v4[2], 30, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18007c1b0  push    rbx
0x18007c1b2  push    rbp
0x18007c1b3  push    rsi
0x18007c1b4  push    rdi
0x18007c1b5  sub     rsp, 28h
0x18007c1b9  mov     esi, edx
0x18007c1bb  mov     rbx, rcx
0x18007c1be  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c1c5  lea     rbp, WPP_GLOBAL_Control
0x18007c1cc  cmp     rcx, rbp
0x18007c1cf  jz      short loc_18007C1F3
0x18007c1d1  test    byte ptr [rcx+1Ch], 1
0x18007c1d5  jz      short loc_18007C1F3
0x18007c1d7  mov     rcx, [rcx+10h]
0x18007c1db  lea     r8, WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids
0x18007c1e2  mov     edx, 1Ch
0x18007c1e7  call    WPP_SF_
0x18007c1ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c1f3  test    rbx, rbx
0x18007c1f6  jnz     short loc_18007C228
0x18007c1f8  mov     ebx, 6
0x18007c1fd  cmp     rcx, rbp
0x18007c200  jz      loc_18007C2ED
0x18007c206  test    byte ptr [rcx+1Ch], 2
0x18007c20a  jz      loc_18007C2CA
0x18007c210  mov     rcx, [rcx+10h]
0x18007c214  lea     edx, [rbx+17h]
0x18007c217  lea     r8, WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids
0x18007c21e  call    WPP_SF_
0x18007c223  jmp     loc_18007C2C3
0x18007c228  xor     edi, edi
0x18007c22a  lea     r8, aAuthportmgrfin; "AuthPortMgrFindInGlobalListAndRemove"
0x18007c231  mov     r9d, 0EDh
0x18007c237  lea     rdx, qword_1800BB520
0x18007c23e  lea     rcx, g_WcnOneXInfo
0x18007c245  call    cs:__imp_AcquireWriteLock
0x18007c24c  nop     dword ptr [rax+rax+00h]
0x18007c251  mov     rax, cs:qword_1800BB510
0x18007c258  lea     rcx, qword_1800BB510
0x18007c25f  cmp     rax, rcx
0x18007c262  jz      short loc_18007C290
0x18007c264  cmp     rbx, rax
0x18007c267  jz      short loc_18007C26E
0x18007c269  mov     rax, [rax]
0x18007c26c  jmp     short loc_18007C258
0x18007c26e  test    esi, esi
0x18007c270  jz      short loc_18007C28B
0x18007c272  mov     rcx, [rax]
0x18007c275  cmp     [rcx+8], rax
0x18007c279  jnz     short loc_18007C2F9
0x18007c27b  mov     rdx, [rax+8]
0x18007c27f  cmp     [rdx], rax
0x18007c282  jnz     short loc_18007C2F9
0x18007c284  mov     [rdx], rcx
0x18007c287  mov     [rcx+8], rdx
0x18007c28b  mov     edi, 1
0x18007c290  mov     r9d, 102h
0x18007c296  lea     r8, aAuthportmgrfin; "AuthPortMgrFindInGlobalListAndRemove"
0x18007c29d  lea     rdx, qword_1800BB520
0x18007c2a4  lea     rcx, g_WcnOneXInfo
0x18007c2ab  call    cs:__imp_ReleaseWriteLock
0x18007c2b2  nop     dword ptr [rax+rax+00h]
0x18007c2b7  neg     edi
0x18007c2b9  sbb     ebx, ebx
0x18007c2bb  not     ebx
0x18007c2bd  and     ebx, 490h
0x18007c2c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c2ca  cmp     rcx, rbp
0x18007c2cd  jz      short loc_18007C2ED
0x18007c2cf  test    byte ptr [rcx+1Ch], 1
0x18007c2d3  jz      short loc_18007C2ED
0x18007c2d5  mov     rcx, [rcx+10h]
0x18007c2d9  lea     r8, WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids
0x18007c2e0  mov     edx, 1Eh
0x18007c2e5  mov     r9d, ebx
0x18007c2e8  call    WPP_SF_d
0x18007c2ed  mov     eax, ebx
0x18007c2ef  add     rsp, 28h
0x18007c2f3  pop     rdi
0x18007c2f4  pop     rsi
0x18007c2f5  pop     rbp
0x18007c2f6  pop     rbx
0x18007c2f7  retn
0x18007c2f9  mov     ecx, 3
0x18007c2fe  int     29h; Win8: RtlFailFast(ecx)
```
