# RtmReleaseDestInfo

- ea: `0x180007220`
- end: `0x1800072cb`
- name: `RtmReleaseDestInfo`
- size: `171`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, PRTM_DEST_INFO DestInfo)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180004220`
- `0x180006990`
- `0x180006ca0`
- `0x180017a44`
- `0x180018070`
- `0x18001958c`
- `0x18001decc`

## callees

- `0x180007220`
- `0x180009adc`
- `0x18000a1bc`
- `0x18000a298`

## pseudocode

```c
DWORD __stdcall RtmReleaseDestInfo(RTM_ENTITY_HANDLE RtmRegHandle, PRTM_DEST_INFO DestInfo)
{
  __int64 i; // rdi
  unsigned __int64 Route; // rcx
  volatile signed __int32 *v5; // rcx
  char *v6; // rcx
  unsigned __int64 HoldRoute; // rcx
  volatile signed __int32 *v8; // rcx
  LPVOID *v9; // rcx

  for ( i = 0; (unsigned int)i < DestInfo->NumberOfViews; i = (unsigned int)(i + 1) )
  {
    Route = (unsigned __int64)DestInfo->ViewInfo[i].Route;
    if ( Route )
    {
      v5 = (volatile signed __int32 *)(Route ^ 0x7754DF32);
      if ( _InterlockedExchangeAdd(v5, 0xFFFFFFFF) == 1 )
        DestroyRoute(v5);
      v6 = (char *)((__int64)DestInfo->ViewInfo[i].Owner ^ 0x7754DF32);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
        DestroyEntity(v6);
    }
    HoldRoute = (unsigned __int64)DestInfo->ViewInfo[i].HoldRoute;
    if ( HoldRoute )
    {
      v8 = (volatile signed __int32 *)(HoldRoute ^ 0x7754DF32);
      if ( _InterlockedExchangeAdd(v8, 0xFFFFFFFF) == 1 )
        DestroyRoute(v8);
    }
  }
  v9 = (LPVOID *)((__int64)DestInfo->DestHandle ^ 0x7754DF32);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9, 0xFFFFFFFF) == 1 )
    DestroyDest(v9);
  return 0;
}

```

## disassembly

```asm
0x180007220  push    rbx
0x180007222  push    rbp
0x180007223  push    rsi
0x180007224  push    rdi
0x180007225  push    r14
0x180007227  push    r15
0x180007229  sub     rsp, 28h
0x18000722d  xor     edi, edi
0x18000722f  or      r14d, 0FFFFFFFFh
0x180007233  mov     rbx, rdx
0x180007236  mov     r15d, 7754DF32h
0x18000723c  cmp     [rdx+28h], edi
0x18000723f  jbe     short loc_1800072A5
0x180007241  lea     rbp, [rdi+rdi*4]
0x180007245  mov     rcx, [rbx+rbp*8+38h]
0x18000724a  test    rcx, rcx
0x18000724d  jz      short loc_18000727C
0x18000724f  xor     rcx, r15; lpMem
0x180007252  mov     eax, r14d
0x180007255  lock xadd [rcx], eax
0x180007259  add     eax, r14d
0x18000725c  jnz     short loc_180007263
0x18000725e  call    DestroyRoute
0x180007263  mov     rcx, [rbx+rbp*8+40h]
0x180007268  mov     eax, r14d
0x18000726b  xor     rcx, r15; lpMem
0x18000726e  lock xadd [rcx], eax
0x180007272  add     eax, r14d
0x180007275  jnz     short loc_18000727C
0x180007277  call    DestroyEntity
0x18000727c  lea     rax, [rdi+rdi*4]
0x180007280  mov     rcx, [rbx+rax*8+50h]
0x180007285  test    rcx, rcx
0x180007288  jz      short loc_18000729E
0x18000728a  xor     rcx, r15; lpMem
0x18000728d  mov     eax, r14d
0x180007290  lock xadd [rcx], eax
0x180007294  add     eax, r14d
0x180007297  jnz     short loc_18000729E
0x180007299  call    DestroyRoute
0x18000729e  inc     edi
0x1800072a0  cmp     edi, [rbx+28h]
0x1800072a3  jb      short loc_180007241
0x1800072a5  mov     rcx, [rbx]
0x1800072a8  mov     eax, r14d
0x1800072ab  xor     rcx, r15; lpMem
0x1800072ae  lock xadd [rcx], eax
0x1800072b2  add     eax, r14d
0x1800072b5  jnz     short loc_1800072BC
0x1800072b7  call    DestroyDest
0x1800072bc  xor     eax, eax
0x1800072be  add     rsp, 28h
0x1800072c2  pop     r15
0x1800072c4  pop     r14
0x1800072c6  pop     rdi
0x1800072c7  pop     rsi
0x1800072c8  pop     rbp
0x1800072c9  pop     rbx
0x1800072ca  retn
```
