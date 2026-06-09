# UdfWriteSparingTable

- ea: `0x14001b938`
- end: `0x14001ba1b`
- name: `UdfWriteSparingTable`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000ba88`

## callees

- `0x140009450`
- `0x14000c36c`
- `0x14001093c`
- `0x14001b938`

## pseudocode

```c
__int64 __fastcall UdfWriteSparingTable(__int64 a1)
{
  __int64 v1; // rdi
  int v2; // r14d
  unsigned int v3; // ebp
  __int64 v4; // rsi
  int v5; // r8d

  v1 = 0;
  v2 = a1;
  v3 = -1073741668;
  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL);
  ++*(_DWORD *)(*(_QWORD *)(v4 + 56) + 52LL);
  if ( *(_DWORD *)(v4 + 8) )
  {
    do
    {
      *(_DWORD *)(*(_QWORD *)(v4 + 56) + 12LL) = *(_DWORD *)(v4 + 4 * v1 + 12);
      UdfUpdateChecksumAndCrc(*(_QWORD *)(v4 + 56), 8 * *(unsigned __int16 *)(*(_QWORD *)(v4 + 56) + 48LL) + 56);
      v5 = UdfRmwReadWriteSectors(v2, 1, 3);
      if ( v5 >= 0 )
      {
        v3 = v5;
      }
      else if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
      {
        WPP_SF_dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          36,
          WPP_e04914546632397e8b30a0a107c62418_Traceguids,
          (unsigned int)v1,
          v5);
      }
      v1 = (unsigned int)(v1 + 1);
    }
    while ( (unsigned int)v1 < *(_DWORD *)(v4 + 8) );
  }
  return v3;
}

```

## disassembly

```asm
0x14001b938  push    rbx
0x14001b93a  push    rbp
0x14001b93b  push    rsi
0x14001b93c  push    rdi
0x14001b93d  push    r14
0x14001b93f  sub     rsp, 30h
0x14001b943  mov     rax, [rcx+10h]
0x14001b947  xor     edi, edi
0x14001b949  mov     r14, rcx
0x14001b94c  mov     ebp, 0C000009Ch
0x14001b951  mov     rsi, [rax+10h]
0x14001b955  mov     rax, [rsi+38h]
0x14001b959  inc     dword ptr [rax+34h]
0x14001b95c  cmp     [rsi+8], edi
0x14001b95f  jbe     loc_14001BA0D
0x14001b965  mov     rcx, [rsi+38h]
0x14001b969  mov     eax, [rsi+rdi*4+0Ch]
0x14001b96d  mov     [rcx+0Ch], eax
0x14001b970  mov     rcx, [rsi+38h]
0x14001b974  movzx   edx, word ptr [rcx+30h]
0x14001b978  lea     edx, ds:38h[rdx*8]
0x14001b97f  call    UdfUpdateChecksumAndCrc
0x14001b984  mov     rcx, [r14+10h]
0x14001b988  mov     r8d, [rsi+28h]
0x14001b98c  mov     r9, [rsi+38h]
0x14001b990  dec     r8d
0x14001b993  mov     [rsp+58h+var_30], 3
0x14001b99b  mov     edx, [rcx+44h]
0x14001b99e  add     r8d, edx
0x14001b9a1  mov     ecx, [rcx+48h]
0x14001b9a4  neg     edx
0x14001b9a6  and     r8d, edx
0x14001b9a9  mov     byte ptr [rsp+58h+var_38], 1
0x14001b9ae  mov     edx, [rsi+rdi*4+0Ch]
0x14001b9b2  shr     r8d, cl
0x14001b9b5  mov     rcx, r14
0x14001b9b8  call    UdfRmwReadWriteSectors
0x14001b9bd  mov     r8d, eax
0x14001b9c0  test    eax, eax
0x14001b9c2  jns     short loc_14001B9FF
0x14001b9c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b9cb  lea     rax, WPP_GLOBAL_Control
0x14001b9d2  cmp     rcx, rax
0x14001b9d5  jz      short loc_14001BA02
0x14001b9d7  test    dword ptr [rcx+2Ch], 20000000h
0x14001b9de  jz      short loc_14001BA02
0x14001b9e0  mov     rcx, [rcx+18h]
0x14001b9e4  mov     edx, 24h ; '$'
0x14001b9e9  mov     [rsp+58h+var_38], r8d
0x14001b9ee  mov     r9d, edi
0x14001b9f1  lea     r8, WPP_e04914546632397e8b30a0a107c62418_Traceguids
0x14001b9f8  call    WPP_SF_dd
0x14001b9fd  jmp     short loc_14001BA02
0x14001b9ff  mov     ebp, r8d
0x14001ba02  inc     edi
0x14001ba04  cmp     edi, [rsi+8]
0x14001ba07  jb      loc_14001B965
0x14001ba0d  mov     eax, ebp
0x14001ba0f  add     rsp, 30h
0x14001ba13  pop     r14
0x14001ba15  pop     rdi
0x14001ba16  pop     rsi
0x14001ba17  pop     rbp
0x14001ba18  pop     rbx
0x14001ba19  retn
```
