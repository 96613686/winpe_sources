# XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::WriteLog(XE_Log *,unsigned __int64,void const * const,uint)

- ea: `0x10043c790`
- end: `0x10043c86b`
- name: `?WriteLog@?$XE_FileWriter@V?$XE_FileWriterDefaultPolicy@$00$1?DefaultFileExtension@XEPackage0@@3PA_WA@@VXE_MetadataTracker@@@@AEAAHPEAVXE_Log@@_KQEBXI@Z`
- size: `219`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x10043c550`
- `0x1005c0470`

## callees

- `0x10043c790`

## import_xrefs

- `KERNEL32!WriteFile` at `0x10043c816`
- `KERNEL32!WriteFile` at `0x1005beecf`
- `KERNEL32!WriteFile` at `0x10043c816`
- `KERNEL32!WriteFile` at `0x1005beecf`
- `KERNEL32!GetLastError` at `0x1005bedaa`
- `KERNEL32!GetLastError` at `0x1005bee65`
- `KERNEL32!GetLastError` at `0x1005bedaa`
- `KERNEL32!GetLastError` at `0x1005bee65`

## pseudocode

```c
__int64 __fastcall XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::WriteLog(
        __int64 a1,
        __int64 a2,
        char *a3,
        char *a4,
        DWORD nNumberOfBytesToWrite)
{
  char *v5; // r10
  unsigned __int64 v6; // r12
  void *v10; // rcx
  bool v11; // zf
  unsigned int v12; // eax
  unsigned int v13; // edi
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rtt
  __int64 result; // rax
  unsigned int v18; // eax
  unsigned int v19; // r15d
  unsigned int v20; // ebx
  void *v21; // rcx
  DWORD v22; // ebp
  char *v23; // rdx
  unsigned int v24; // eax
  DWORD LastError; // eax
  unsigned int v26; // ebx
  struct _OVERLAPPED lpOverlapped; // [rsp+30h] [rbp-78h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-58h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+B0h] [rbp+8h] BYREF
  char *v30; // [rsp+C8h] [rbp+20h]

  v30 = a4;
  v5 = a4;
  v6 = nNumberOfBytesToWrite;
  if ( nNumberOfBytesToWrite > *(_DWORD *)(a1 + 1672) )
  {
LABEL_15:
    v19 = 0;
    while ( 1 )
    {
      v20 = *(_DWORD *)(a1 + 1672);
      v21 = *(void **)(a2 + 632);
      NumberOfBytesWritten = 0;
      v22 = v20;
      Overlapped.Internal = 0;
      if ( (unsigned int)v6 - v19 < v20 )
        v22 = v6 - v19;
      Overlapped.InternalHigh = 0;
      Overlapped.hEvent = 0;
      Overlapped.Pointer = &a3[v19];
      v23 = &v5[v19];
      if ( *(_DWORD *)(a2 + 52) )
        v24 = qword_100715070(v21, v23, v22, &NumberOfBytesWritten, &Overlapped);
      else
        v24 = WriteFile(v21, v23, v22, &NumberOfBytesWritten, &Overlapped);
      v13 = v24;
      if ( v24 )
      {
        v19 += v22;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError != 1450 )
        {
          v11 = LastError == 112;
          result = v13;
          if ( v11 )
            *(_DWORD *)(a2 + 48) = 1;
          return result;
        }
        if ( v20 <= 0xA00000 )
          return v13;
        v26 = v20 >> 17 << 16;
        if ( v26 < *(_DWORD *)(a1 + 1672) && v26 >= 0xA00000 )
          *(_DWORD *)(a1 + 1672) = v26;
        v13 = 1;
      }
      if ( v19 >= (unsigned int)v6 )
        goto LABEL_5;
      v5 = v30;
    }
  }
  v10 = *(void **)(a2 + 632);
  v11 = *(_DWORD *)(a2 + 52) == 0;
  lpOverlapped.Internal = 0;
  lpOverlapped.InternalHigh = 0;
  lpOverlapped.hEvent = 0;
  lpOverlapped.Pointer = a3;
  nNumberOfBytesToWrite = 0;
  _mm_lfence();
  if ( v11 )
    v12 = WriteFile(v10, a4, v6, &nNumberOfBytesToWrite, &lpOverlapped);
  else
    v12 = qword_100715070(v10, a4, (unsigned int)v6, &nNumberOfBytesToWrite, &lpOverlapped);
  v13 = v12;
  if ( !v12 )
  {
    if ( GetLastError() == 1450 && (v18 = (unsigned int)v6 >> 17 << 16, v18 < *(_DWORD *)(a1 + 1672)) )
    {
      v5 = v30;
      if ( v18 >= 0xA00000 )
        *(_DWORD *)(a1 + 1672) = v18;
    }
    else
    {
      v5 = v30;
    }
    goto LABEL_15;
  }
LABEL_5:
  v14 = *(_QWORD *)(a2 + 648);
  v15 = (unsigned __int64)&a3[v6];
  while ( v14 < v15 )
  {
    v16 = v14;
    v14 = _InterlockedCompareExchange64((volatile signed __int64 *)(a2 + 648), v15, v14);
    if ( v16 == v14 )
      break;
    _mm_pause();
  }
  _InterlockedExchangeAdd64((volatile signed __int64 *)(a1 + 1936), v6);
  return v13;
}

```

## disassembly

```asm
0x10043c790  mov     r11, rsp
0x10043c793  mov     [r11+10h], rbx
0x10043c797  mov     [r11+20h], r9
0x10043c79b  push    rbp
0x10043c79c  push    rsi
0x10043c79d  push    rdi
0x10043c79e  push    r12
0x10043c7a0  push    r13
0x10043c7a2  push    r14
0x10043c7a4  push    r15
0x10043c7a6  sub     rsp, 70h
0x10043c7aa  mov     eax, [rcx+688h]
0x10043c7b0  mov     r10, r9
0x10043c7b3  mov     r12d, [rsp+0A8h+nNumberOfBytesToWrite]
0x10043c7bb  xor     r9d, r9d
0x10043c7be  mov     r13, r8
0x10043c7c1  mov     rsi, rdx
0x10043c7c4  mov     r14, rcx
0x10043c7c7  cmp     r12d, eax
0x10043c7ca  ja      loc_1005BEDED
0x10043c7d0  mov     rcx, [rdx+278h]; hFile
0x10043c7d7  mov     rax, r8
0x10043c7da  shr     rax, 20h
0x10043c7de  mov     r8d, r12d; nNumberOfBytesToWrite
0x10043c7e1  cmp     [rdx+34h], r9d
0x10043c7e5  mov     [r11-78h], r9
0x10043c7e9  mov     [r11-70h], r9
0x10043c7ed  mov     [r11-60h], r9
0x10043c7f1  mov     [r11-68h], r13d
0x10043c7f5  mov     [rsp+0A8h+var_64], eax
0x10043c7f9  lea     rax, [r11-78h]
0x10043c7fd  mov     [rsp+0A8h+lpOverlapped], rax; lpOverlapped
0x10043c802  mov     [r11+28h], r9d
0x10043c806  lfence
0x10043c809  lea     r9, [r11+28h]; lpNumberOfBytesWritten
0x10043c80d  mov     rdx, r10; lpBuffer
0x10043c810  jnz     loc_1005BED9E
0x10043c816  call    cs:__imp_WriteFile
0x10043c81c  mov     edi, eax
0x10043c81e  test    eax, eax
0x10043c820  jz      loc_1005BEDAA
0x10043c826  mov     rax, [rsi+288h]
0x10043c82d  lea     rcx, [r12+r13]
0x10043c831  mov     rdx, r12
0x10043c834  cmp     rax, rcx
0x10043c837  jnb     short loc_10043C848
0x10043c839  lock cmpxchg [rsi+288h], rcx
0x10043c842  jnz     loc_1005BEEF7
0x10043c848  lock xadd [r14+790h], rdx
0x10043c851  mov     eax, edi
0x10043c853  mov     rbx, [rsp+0A8h+arg_8]
0x10043c85b  add     rsp, 70h
0x10043c85f  pop     r15
0x10043c861  pop     r14
0x10043c863  pop     r13
0x10043c865  pop     r12
0x10043c867  pop     rdi
0x10043c868  pop     rsi
0x10043c869  pop     rbp
0x10043c86a  retn
0x1005bed9e  call    cs:qword_100715070
0x1005beda4  jmp     loc_10043C81C
0x1005bedaa  call    cs:__imp_GetLastError
0x1005bedb0  cmp     eax, 5AAh
0x1005bedb5  jnz     loc_1005BEEBE
0x1005bedbb  mov     eax, r12d
0x1005bedbe  shr     eax, 11h
0x1005bedc1  shl     eax, 10h
0x1005bedc4  cmp     eax, [r14+688h]
0x1005bedcb  jnb     loc_1005BEEBE
0x1005bedd1  mov     r10, [rsp+0A8h+arg_18]
0x1005bedd9  xor     r9d, r9d
0x1005beddc  cmp     eax, 0A00000h
0x1005bede1  jb      short loc_1005BEDED
0x1005bede3  mov     [r14+688h], eax
0x1005bedea  jmp     short loc_1005BEDED
0x1005beded  mov     r15d, r9d
0x1005bedf0  mov     ebx, [r14+688h]
0x1005bedf7  mov     eax, r12d
0x1005bedfa  mov     rcx, [rsi+278h]; hFile
0x1005bee01  sub     eax, r15d
0x1005bee04  cmp     eax, ebx
0x1005bee06  mov     [rsp+0A8h+NumberOfBytesWritten], r9d
0x1005bee0e  mov     ebp, ebx
0x1005bee10  mov     [rsp+0A8h+Overlapped.Internal], r9
0x1005bee15  cmovb   ebp, eax
0x1005bee18  mov     [rsp+0A8h+Overlapped.InternalHigh], r9
0x1005bee1d  mov     eax, r15d
0x1005bee20  mov     [rsp+0A8h+Overlapped.hEvent], r9
0x1005bee25  lea     r9, [rsp+0A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1005bee2d  lea     r8, [rax+r13]
0x1005bee31  mov     dword ptr [rsp+0A8h+Overlapped.10h], r8d
0x1005bee36  lea     rdx, [rax+r10]; lpBuffer
0x1005bee3a  shr     r8, 20h
0x1005bee3e  lea     rax, [rsp+0A8h+Overlapped]
0x1005bee43  cmp     dword ptr [rsi+34h], 0
0x1005bee47  mov     dword ptr [rsp+0A8h+Overlapped.10h+4], r8d
0x1005bee4c  mov     r8d, ebp; nNumberOfBytesToWrite
0x1005bee4f  mov     [rsp+0A8h+lpOverlapped], rax; lpOverlapped
0x1005bee54  jz      short loc_1005BEECF
0x1005bee56  call    cs:qword_100715070
0x1005bee5c  jmp     short loc_1005BEE5F
0x1005bee5f  mov     edi, eax
0x1005bee61  test    eax, eax
0x1005bee63  jnz     short loc_1005BEED9
0x1005bee65  call    cs:__imp_GetLastError
0x1005bee6b  cmp     eax, 5AAh
0x1005bee70  jnz     short loc_1005BEEDF
0x1005bee72  cmp     ebx, 0A00000h
0x1005bee78  jbe     loc_10043C851
0x1005bee7e  shr     ebx, 11h
0x1005bee81  shl     ebx, 10h
0x1005bee84  cmp     ebx, [r14+688h]
0x1005bee8b  jnb     short loc_1005BEE9C
0x1005bee8d  cmp     ebx, 0A00000h
0x1005bee93  jb      short loc_1005BEE9C
0x1005bee95  mov     [r14+688h], ebx
0x1005bee9c  mov     edi, 1
0x1005beea1  jmp     short loc_1005BEEA4
0x1005beea4  cmp     r15d, r12d
0x1005beea7  jnb     loc_10043C826
0x1005beead  mov     r10, [rsp+0A8h+arg_18]
0x1005beeb5  xor     r9d, r9d
0x1005beeb8  jmp     loc_1005BEDF0
0x1005beebe  mov     r10, [rsp+0A8h+arg_18]
0x1005beec6  xor     r9d, r9d
0x1005beec9  jmp     loc_1005BEDED
0x1005beecf  call    cs:__imp_WriteFile
0x1005beed5  nop
0x1005beed6  jmp     short loc_1005BEE5F
0x1005beed9  add     r15d, ebp
0x1005beedc  jmp     short loc_1005BEEA4
0x1005beedf  cmp     eax, 70h ; 'p'
0x1005beee2  mov     eax, edi
0x1005beee4  jnz     loc_10043C853
0x1005beeea  mov     dword ptr [rsi+30h], 1
0x1005beef1  jmp     loc_10043C853
0x1005beef7  pause
0x1005beef9  cmp     rax, rcx
0x1005beefc  jnb     loc_10043C848
0x1005bef02  jmp     loc_10043C839
```
