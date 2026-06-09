# RtmCreateDestEnum

- ea: `0x180005a00`
- end: `0x180005bf1`
- name: `RtmCreateDestEnum`
- size: `497`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_VIEW_SET TargetViews, RTM_ENUM_FLAGS EnumFlags, PRTM_NET_ADDRESS NetAddress, ULONG ProtocolId, PRTM_ENUM_HANDLE RtmEnumHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005dc0`

## callees

- `0x180005a00`
- `0x18001f952`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180005a82`
- `KERNEL32!HeapAlloc` at `0x180005a82`
- `KERNEL32!GetProcessHeap` at `0x180005a70`
- `KERNEL32!GetProcessHeap` at `0x180005ba3`
- `KERNEL32!GetProcessHeap` at `0x180005a70`
- `KERNEL32!GetProcessHeap` at `0x180005ba3`
- `KERNEL32!HeapFree` at `0x180005bb3`
- `KERNEL32!HeapFree` at `0x180005bb3`
- `KERNEL32!InitializeCriticalSection` at `0x180005b52`
- `KERNEL32!InitializeCriticalSection` at `0x180005b52`
- `KERNEL32!DeleteCriticalSection` at `0x180005b9d`
- `KERNEL32!DeleteCriticalSection` at `0x180005b9d`

## pseudocode

```c
DWORD __stdcall RtmCreateDestEnum(
        RTM_ENTITY_HANDLE RtmRegHandle,
        RTM_VIEW_SET TargetViews,
        RTM_ENUM_FLAGS EnumFlags,
        PRTM_NET_ADDRESS NetAddress,
        ULONG ProtocolId,
        PRTM_ENUM_HANDLE RtmEnumHandle)
{
  RTM_VIEW_SET v8; // edi
  volatile signed __int32 *v9; // rsi
  RTM_ENUM_FLAGS v10; // r12d
  __int64 v11; // r13
  HANDLE ProcessHeap; // rax
  _BYTE *v14; // rax
  int v15; // edx
  unsigned __int64 v16; // rbx
  int i; // ecx
  unsigned int v18; // r13d
  __int64 v19; // rdi

  v8 = TargetViews;
  v9 = (volatile signed __int32 *)((unsigned __int64)RtmRegHandle ^ 0x7754DF32);
  if ( (unsigned __int64)RtmRegHandle == 0x7754DF32
    || *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) == 1 )
  {
    return 6;
  }
  v10 = EnumFlags & 3;
  if ( v10 == 3 || (EnumFlags & 3) != 0 && !NetAddress )
    return 87;
  v11 = *(_QWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x10);
  if ( (~*(_DWORD *)(v11 + 40) & TargetViews) != 0 )
    return 50;
  ProcessHeap = GetProcessHeap();
  v14 = HeapAlloc(ProcessHeap, 8u, 0x70u);
  v16 = (unsigned __int64)v14;
  if ( !v14 )
    return 8;
  v14[4] = 7;
  *((_DWORD *)v14 + 2) = v8;
  for ( i = 0; v8; v8 &= v8 - 1 )
    ++i;
  *((_DWORD *)v14 + 3) = i;
  *((_DWORD *)v14 + 4) = ProtocolId;
  *((_DWORD *)v14 + 5) = EnumFlags;
  if ( (EnumFlags & 2) != 0 )
  {
    v18 = *(_DWORD *)(v11 + 8);
    *((_WORD *)v14 + 12) = NetAddress->AddressFamily;
    *((_WORD *)v14 + 13) = 8 * v18;
    v19 = 0;
    if ( (NetAddress->NumBits & 0xFFF8) != 0 )
    {
      do
      {
        v14[v19 + 28] = NetAddress->AddrBits[v19];
        v19 = (unsigned int)(v19 + 1);
      }
      while ( (unsigned int)v19 < NetAddress->NumBits >> 3 );
    }
    if ( (unsigned int)v19 < v18 )
    {
      LOBYTE(v15) = -1;
      memset_0(&v14[(unsigned int)v19 + 28], v15, v18 - (unsigned int)v19);
      *(_BYTE *)((unsigned int)v19 + v16 + 28) >>= NetAddress->NumBits & 7;
      *(_BYTE *)((unsigned int)v19 + v16 + 28) |= NetAddress->AddrBits[(unsigned int)v19];
    }
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)(v16 + 48));
  if ( v10 )
  {
    *(_OWORD *)(v16 + 92) = *(_OWORD *)&NetAddress->AddressFamily;
    *(_DWORD *)(v16 + 108) = *(_DWORD *)&NetAddress->AddrBits[12];
  }
  _InterlockedIncrement(v9);
  *RtmEnumHandle = (HANDLE)(v16 ^ 0x7754DF32);
  return 0;
}

```

## disassembly

```asm
0x180005a00  mov     [rsp+arg_8], rbx
0x180005a05  mov     [rsp+arg_10], rsi
0x180005a0a  push    rdi
0x180005a0b  push    r12
0x180005a0d  push    r13
0x180005a0f  push    r14
0x180005a11  push    r15
0x180005a13  sub     rsp, 30h
0x180005a17  mov     r15, r9
0x180005a1a  mov     r14d, r8d
0x180005a1d  mov     edi, edx
0x180005a1f  mov     rsi, rcx
0x180005a22  xor     rsi, 7754DF32h
0x180005a29  jz      loc_180005BD4
0x180005a2f  cmp     dword ptr [rsi+30h], 1
0x180005a33  jz      loc_180005BD4
0x180005a39  mov     r12d, r8d
0x180005a3c  and     r12d, 3
0x180005a40  cmp     r12d, 3
0x180005a44  jz      loc_180005BCD
0x180005a4a  test    r12d, r12d
0x180005a4d  jz      short loc_180005A58
0x180005a4f  test    r9, r9
0x180005a52  jz      loc_180005BCD
0x180005a58  mov     r13, [rsi+10h]
0x180005a5c  mov     eax, [r13+28h]
0x180005a60  not     eax
0x180005a62  test    edi, eax
0x180005a64  jz      short loc_180005A70
0x180005a66  mov     eax, 32h ; '2'
0x180005a6b  jmp     loc_180005BD9
0x180005a70  call    cs:__imp_GetProcessHeap
0x180005a76  mov     rcx, rax; hHeap
0x180005a79  mov     edx, 8; dwFlags
0x180005a7e  lea     r8d, [rdx+68h]; dwBytes
0x180005a82  call    cs:__imp_HeapAlloc
0x180005a88  mov     rbx, rax
0x180005a8b  mov     [rsp+58h+lpMem], rax
0x180005a90  test    rax, rax
0x180005a93  jnz     short loc_180005A9F
0x180005a95  mov     eax, 8
0x180005a9a  jmp     loc_180005BD9
0x180005a9f  mov     byte ptr [rax+4], 7
0x180005aa3  mov     [rax+8], edi
0x180005aa6  xor     ecx, ecx
0x180005aa8  test    edi, edi
0x180005aaa  jz      short loc_180005AB5
0x180005aac  lea     eax, [rdi-1]
0x180005aaf  inc     ecx
0x180005ab1  and     edi, eax
0x180005ab3  jnz     short loc_180005AAC
0x180005ab5  mov     [rbx+0Ch], ecx
0x180005ab8  mov     eax, [rsp+58h+ProtocolId]
0x180005abf  mov     [rbx+10h], eax
0x180005ac2  mov     [rbx+14h], r14d
0x180005ac6  test    r14b, 2
0x180005aca  jz      short loc_180005B46
0x180005acc  mov     r13d, [r13+8]
0x180005ad0  movzx   eax, word ptr [r15]
0x180005ad4  mov     [rbx+18h], ax
0x180005ad8  movzx   eax, r13w
0x180005adc  shl     ax, 3
0x180005ae0  mov     [rbx+1Ah], ax
0x180005ae4  xor     edi, edi
0x180005ae6  movzx   eax, word ptr [r15+2]
0x180005aeb  test    eax, 0FFFFFFF8h
0x180005af0  jbe     short loc_180005B09
0x180005af2  mov     al, [rdi+r15+4]
0x180005af7  mov     [rdi+rbx+1Ch], al
0x180005afb  inc     edi
0x180005afd  movzx   eax, word ptr [r15+2]
0x180005b02  shr     eax, 3
0x180005b05  cmp     edi, eax
0x180005b07  jb      short loc_180005AF2
0x180005b09  mov     r14d, edi
0x180005b0c  cmp     edi, r13d
0x180005b0f  jnb     short loc_180005B46
0x180005b11  mov     r8d, r13d
0x180005b14  sub     r8d, edi; Size
0x180005b17  lea     rcx, [rbx+1Ch]
0x180005b1b  add     rcx, r14; void *
0x180005b1e  mov     dl, 0FFh; Val
0x180005b20  call    memset_0
0x180005b25  cmp     edi, r13d
0x180005b28  jnb     short loc_180005B46
0x180005b2a  movzx   ecx, word ptr [r15+2]
0x180005b2f  and     ecx, 7
0x180005b32  shr     byte ptr [r14+rbx+1Ch], cl
0x180005b37  mov     al, [r14+rbx+1Ch]
0x180005b3c  or      al, [r14+r15+4]
0x180005b41  mov     [r14+rbx+1Ch], al
0x180005b46  mov     [rsp+58h+var_38], 0
0x180005b4e  lea     rcx, [rbx+30h]; lpCriticalSection
0x180005b52  call    cs:__imp_InitializeCriticalSection
0x180005b58  mov     [rsp+58h+var_38], 1
0x180005b60  test    r12d, r12d
0x180005b63  jz      short loc_180005B74
0x180005b65  movups  xmm0, xmmword ptr [r15]
0x180005b69  movups  xmmword ptr [rbx+5Ch], xmm0
0x180005b6d  mov     eax, [r15+10h]
0x180005b71  mov     [rbx+6Ch], eax
0x180005b74  lock inc dword ptr [rsi]
0x180005b77  xor     rbx, 7754DF32h
0x180005b7e  mov     rax, [rsp+58h+RtmEnumHandle]
0x180005b86  mov     [rax], rbx
0x180005b89  xor     eax, eax
0x180005b8b  jmp     short loc_180005BD9
0x180005b8d  cmp     [rsp+58h+var_38], 0
0x180005b92  jz      short loc_180005BA3
0x180005b94  mov     rcx, [rsp+58h+lpMem]
0x180005b99  add     rcx, 30h ; '0'; lpCriticalSection
0x180005b9d  call    cs:__imp_DeleteCriticalSection
0x180005ba3  call    cs:__imp_GetProcessHeap
0x180005ba9  mov     rcx, rax; hHeap
0x180005bac  mov     r8, [rsp+58h+lpMem]; lpMem
0x180005bb1  xor     edx, edx; dwFlags
0x180005bb3  call    cs:__imp_HeapFree
0x180005bb9  mov     rax, [rsp+58h+RtmEnumHandle]
0x180005bc1  mov     qword ptr [rax], 0
0x180005bc8  jmp     loc_180005A95
0x180005bcd  mov     eax, 57h ; 'W'
0x180005bd2  jmp     short loc_180005BD9
0x180005bd4  mov     eax, 6
0x180005bd9  mov     rbx, [rsp+58h+arg_8]
0x180005bde  mov     rsi, [rsp+58h+arg_10]
0x180005be3  add     rsp, 30h
0x180005be7  pop     r15
0x180005be9  pop     r14
0x180005beb  pop     r13
0x180005bed  pop     r12
0x180005bef  pop     rdi
0x180005bf0  retn
```
