# mciRelaySystemString

- ea: `0x180011428`
- end: `0x180011609`
- name: `mciRelaySystemString`
- size: `481`
- prototype: `__int64 __fastcall(struct tagMCI_SYSTEM_MESSAGE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800025a0`

## callees

- `0x18000b6d4`
- `0x180010504`
- `0x180011428`
- `0x18001a408`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800115b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800115b3`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18001143e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800114a5`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18001143e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800114a5`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x1800114b7`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x1800114da`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x1800114b7`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x1800114da`

## pseudocode

```c
__int64 __fastcall mciRelaySystemString(struct tagMCI_SYSTEM_MESSAGE *a1)
{
  DWORD CurrentDirectoryW; // eax
  DWORD v4; // ebx
  WCHAR *v5; // rax
  WCHAR *v6; // rdi
  unsigned int v7; // ebx

  CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
  if ( CurrentDirectoryW )
  {
    v4 = CurrentDirectoryW + 1;
    v5 = (WCHAR *)winmmAlloc(2 * (CurrentDirectoryW + 1));
    v6 = v5;
    if ( v5 )
    {
      if ( GetCurrentDirectoryW(v4, v5) )
      {
        if ( SetCurrentDirectoryW(*((LPCWSTR *)a1 + 5)) )
        {
          v7 = mciSendStringInternal(0, 0, 0, 0, a1);
          if ( !SetCurrentDirectoryW(v6)
            && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
          }
          v7 = 308;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
        }
        v7 = 307;
      }
      HeapFree(hHeap, 0, v6);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
      }
      return 264;
    }
    return v7;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
    }
    return 277;
  }
}

```

## disassembly

```asm
0x180011428  mov     [rsp+arg_0], rbx
0x18001142d  mov     [rsp+arg_8], rsi
0x180011432  push    rdi
0x180011433  sub     rsp, 30h
0x180011437  mov     rsi, rcx
0x18001143a  xor     edx, edx; lpBuffer
0x18001143c  xor     ecx, ecx; nBufferLength
0x18001143e  call    cs:__imp_GetCurrentDirectoryW
0x180011444  test    eax, eax
0x180011446  jnz     short loc_180011489
0x180011448  mov     rcx, cs:WPP_GLOBAL_Control
0x18001144f  lea     rax, WPP_GLOBAL_Control
0x180011456  cmp     rcx, rax
0x180011459  jz      short loc_18001147F
0x18001145b  test    dword ptr [rcx+1Ch], 400000h
0x180011462  jz      short loc_18001147F
0x180011464  cmp     byte ptr [rcx+19h], 1
0x180011468  jb      short loc_18001147F
0x18001146a  mov     rcx, [rcx+10h]
0x18001146e  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x180011475  mov     edx, 30h ; '0'
0x18001147a  call    WPP_SF_
0x18001147f  mov     eax, 115h
0x180011484  jmp     loc_1800115F9
0x180011489  lea     ebx, [rax+1]
0x18001148c  lea     ecx, [rbx+rbx]; Size
0x18001148f  call    winmmAlloc
0x180011494  mov     rdi, rax
0x180011497  test    rax, rax
0x18001149a  jz      loc_1800115BB
0x1800114a0  mov     rdx, rax; lpBuffer
0x1800114a3  mov     ecx, ebx; nBufferLength
0x1800114a5  call    cs:__imp_GetCurrentDirectoryW
0x1800114ab  test    eax, eax
0x1800114ad  jz      loc_18001156B
0x1800114b3  mov     rcx, [rsi+28h]; lpPathName
0x1800114b7  call    cs:__imp_SetCurrentDirectoryW
0x1800114bd  test    eax, eax
0x1800114bf  jz      short loc_18001152D
0x1800114c1  xor     r9d, r9d; void *
0x1800114c4  mov     [rsp+38h+var_18], rsi; struct tagMCI_SYSTEM_MESSAGE *
0x1800114c9  xor     r8d, r8d; unsigned int
0x1800114cc  xor     edx, edx; unsigned __int16 *
0x1800114ce  xor     ecx, ecx; unsigned __int16 *
0x1800114d0  call    ?mciSendStringInternal@@YAKPEBGPEAGIPEAXPEAUtagMCI_SYSTEM_MESSAGE@@@Z; mciSendStringInternal(ushort const *,ushort *,uint,void *,tagMCI_SYSTEM_MESSAGE *)
0x1800114d5  mov     rcx, rdi; lpPathName
0x1800114d8  mov     ebx, eax
0x1800114da  call    cs:__imp_SetCurrentDirectoryW
0x1800114e0  test    eax, eax
0x1800114e2  jnz     loc_1800115A7
0x1800114e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114ef  lea     rax, WPP_GLOBAL_Control
0x1800114f6  cmp     rcx, rax
0x1800114f9  jz      loc_1800115A7
0x1800114ff  test    dword ptr [rcx+1Ch], 400000h
0x180011506  jz      loc_1800115A7
0x18001150c  cmp     byte ptr [rcx+19h], 1
0x180011510  jb      loc_1800115A7
0x180011516  mov     rcx, [rcx+10h]
0x18001151a  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x180011521  mov     edx, 31h ; '1'
0x180011526  call    WPP_SF_
0x18001152b  jmp     short loc_1800115A7
0x18001152d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011534  lea     rax, WPP_GLOBAL_Control
0x18001153b  cmp     rcx, rax
0x18001153e  jz      short loc_180011564
0x180011540  test    dword ptr [rcx+1Ch], 400000h
0x180011547  jz      short loc_180011564
0x180011549  cmp     byte ptr [rcx+19h], 1
0x18001154d  jb      short loc_180011564
0x18001154f  mov     rcx, [rcx+10h]
0x180011553  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x18001155a  mov     edx, 32h ; '2'
0x18001155f  call    WPP_SF_
0x180011564  mov     ebx, 134h
0x180011569  jmp     short loc_1800115A7
0x18001156b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011572  lea     rax, WPP_GLOBAL_Control
0x180011579  cmp     rcx, rax
0x18001157c  jz      short loc_1800115A2
0x18001157e  test    dword ptr [rcx+1Ch], 400000h
0x180011585  jz      short loc_1800115A2
0x180011587  cmp     byte ptr [rcx+19h], 1
0x18001158b  jb      short loc_1800115A2
0x18001158d  mov     rcx, [rcx+10h]
0x180011591  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x180011598  mov     edx, 33h ; '3'
0x18001159d  call    WPP_SF_
0x1800115a2  mov     ebx, 133h
0x1800115a7  mov     rcx, cs:hHeap; hHeap
0x1800115ae  mov     r8, rdi; lpMem
0x1800115b1  xor     edx, edx; dwFlags
0x1800115b3  call    cs:__imp_HeapFree
0x1800115b9  jmp     short loc_1800115F7
0x1800115bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115c2  lea     rax, WPP_GLOBAL_Control
0x1800115c9  cmp     rcx, rax
0x1800115cc  jz      short loc_1800115F2
0x1800115ce  test    dword ptr [rcx+1Ch], 400000h
0x1800115d5  jz      short loc_1800115F2
0x1800115d7  cmp     byte ptr [rcx+19h], 1
0x1800115db  jb      short loc_1800115F2
0x1800115dd  mov     rcx, [rcx+10h]
0x1800115e1  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x1800115e8  mov     edx, 34h ; '4'
0x1800115ed  call    WPP_SF_
0x1800115f2  mov     ebx, 108h
0x1800115f7  mov     eax, ebx
0x1800115f9  mov     rbx, [rsp+38h+arg_0]
0x1800115fe  mov     rsi, [rsp+38h+arg_8]
0x180011603  add     rsp, 30h
0x180011607  pop     rdi
0x180011608  retn
```
