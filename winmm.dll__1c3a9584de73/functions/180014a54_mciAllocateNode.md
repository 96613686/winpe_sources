# mciAllocateNode

- ea: `0x180014a54`
- end: `0x180014b4b`
- name: `mciAllocateNode`
- size: `247`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180013f64`

## callees

- `0x18000b6d4`
- `0x18001397c`
- `0x180014834`
- `0x180014a54`
- `0x18001a408`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014b11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014b11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014b06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014b06`

## pseudocode

```c
__int64 __fastcall mciAllocateNode(int a1, const unsigned __int16 *a2, struct tagMCI_DEVICE_NODE **a3)
{
  struct tagMCI_DEVICE_NODE *v6; // rax
  struct tagMCI_DEVICE_NODE *v7; // rbx
  __int64 result; // rax
  unsigned int v9; // eax
  DWORD CurrentThreadId; // eax

  v6 = (struct tagMCI_DEVICE_NODE *)winmmAlloc(0x70u);
  v7 = v6;
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids);
    }
    return 0;
  }
  v9 = wReserveDeviceID(v6);
  *((_DWORD *)v7 + 13) = v9;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids);
    }
    goto LABEL_12;
  }
  *((_DWORD *)v7 + 4) = a1;
  CurrentThreadId = GetCurrentThreadId();
  *((_QWORD *)v7 + 10) = CurrentThreadId;
  *((_QWORD *)v7 + 11) = CurrentThreadId;
  if ( (a1 & 0x800) != 0 )
  {
    *((_DWORD *)v7 + 8) = (_DWORD)a2;
  }
  else if ( !mciAddDeviceName(v7, a2) )
  {
LABEL_12:
    HeapFree(hHeap, 0, v7);
    return 0;
  }
  result = *((unsigned int *)v7 + 13);
  *a3 = v7;
  return result;
}

```

## disassembly

```asm
0x180014a54  push    rbx
0x180014a56  push    rsi
0x180014a57  push    rdi
0x180014a58  push    r14
0x180014a5a  sub     rsp, 28h
0x180014a5e  mov     esi, ecx
0x180014a60  mov     r14, r8
0x180014a63  mov     ecx, 70h ; 'p'; Size
0x180014a68  mov     rdi, rdx
0x180014a6b  call    winmmAlloc
0x180014a70  mov     rbx, rax
0x180014a73  test    rax, rax
0x180014a76  jnz     short loc_180014AB4
0x180014a78  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a7f  lea     rax, WPP_GLOBAL_Control
0x180014a86  cmp     rcx, rax
0x180014a89  jz      short loc_180014AAD
0x180014a8b  test    dword ptr [rcx+1Ch], 400000h
0x180014a92  jz      short loc_180014AAD
0x180014a94  cmp     byte ptr [rcx+19h], 1
0x180014a98  jb      short loc_180014AAD
0x180014a9a  mov     rcx, [rcx+10h]
0x180014a9e  lea     edx, [rbx+12h]
0x180014aa1  lea     r8, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids
0x180014aa8  call    WPP_SF_
0x180014aad  xor     eax, eax
0x180014aaf  jmp     loc_180014B41
0x180014ab4  mov     rcx, rbx; struct tagMCI_DEVICE_NODE *
0x180014ab7  call    ?wReserveDeviceID@@YAIPEAUtagMCI_DEVICE_NODE@@@Z; wReserveDeviceID(tagMCI_DEVICE_NODE *)
0x180014abc  mov     [rbx+34h], eax
0x180014abf  test    eax, eax
0x180014ac1  jnz     short loc_180014B0E
0x180014ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x180014aca  lea     rax, WPP_GLOBAL_Control
0x180014ad1  cmp     rcx, rax
0x180014ad4  jz      short loc_180014AFA
0x180014ad6  test    dword ptr [rcx+1Ch], 400000h
0x180014add  jz      short loc_180014AFA
0x180014adf  cmp     byte ptr [rcx+19h], 1
0x180014ae3  jb      short loc_180014AFA
0x180014ae5  mov     rcx, [rcx+10h]
0x180014ae9  lea     r8, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids
0x180014af0  mov     edx, 13h
0x180014af5  call    WPP_SF_
0x180014afa  mov     rcx, cs:hHeap; hHeap
0x180014b01  mov     r8, rbx; lpMem
0x180014b04  xor     edx, edx; dwFlags
0x180014b06  call    cs:__imp_HeapFree
0x180014b0c  jmp     short loc_180014AAD
0x180014b0e  mov     [rbx+10h], esi
0x180014b11  call    cs:__imp_GetCurrentThreadId
0x180014b17  mov     eax, eax
0x180014b19  mov     [rbx+50h], rax
0x180014b1d  mov     [rbx+58h], rax
0x180014b21  bt      esi, 0Bh
0x180014b25  jnb     short loc_180014B2C
0x180014b27  mov     [rbx+20h], edi
0x180014b2a  jmp     short loc_180014B3B
0x180014b2c  mov     rdx, rdi; unsigned __int16 *
0x180014b2f  mov     rcx, rbx; struct tagMCI_DEVICE_NODE *
0x180014b32  call    ?mciAddDeviceName@@YAHPEAUtagMCI_DEVICE_NODE@@PEBG@Z; mciAddDeviceName(tagMCI_DEVICE_NODE *,ushort const *)
0x180014b37  test    eax, eax
0x180014b39  jz      short loc_180014AFA
0x180014b3b  mov     eax, [rbx+34h]
0x180014b3e  mov     [r14], rbx
0x180014b41  add     rsp, 28h
0x180014b45  pop     r14
0x180014b47  pop     rdi
0x180014b48  pop     rsi
0x180014b49  pop     rbx
0x180014b4a  retn
```
