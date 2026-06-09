# midiOutCacheDrumPatches

- ea: `0x1800191b0`
- end: `0x180019260`
- name: `midiOutCacheDrumPatches`
- size: `176`
- prototype: `MMRESULT __stdcall(HMIDIOUT hmo, UINT uPatch, LPWORD pwkya, UINT fuCache)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18001fb58`

## callees

- `0x1800065d0`
- `0x180007560`
- `0x18000c1d0`
- `0x180017aa0`
- `0x1800191b0`

## pseudocode

```c
MMRESULT __stdcall midiOutCacheDrumPatches(HMIDIOUT hmo, UINT uPatch, LPWORD pwkya, UINT fuCache)
{
  unsigned __int16 v4; // di
  unsigned __int16 v6; // bp

  v4 = fuCache;
  v6 = uPatch;
  if ( !pwkya )
    return 11;
  if ( (fuCache & 0xFFFFFFF8) != 0 )
    return 10;
  ClientUpdatePnpInfo();
  if ( !(unsigned int)ValidateHandle(hmo, 3) && !(unsigned int)ValidateHandle(hmo, 9) )
    return 5;
  if ( *((_DWORD *)hmo - 18) == 3 )
    return midiMessage(hmo, 13, pwkya, v4 | (v6 << 16));
  if ( *((_DWORD *)hmo - 18) != 9 )
    return 5;
  return midiStreamBroadcast(hmo, 13, pwkya, v4 | (v6 << 16));
}

```

## disassembly

```asm
0x1800191b0  push    rbx
0x1800191b2  push    rbp
0x1800191b3  push    rsi
0x1800191b4  push    rdi
0x1800191b5  sub     rsp, 28h
0x1800191b9  mov     edi, r9d
0x1800191bc  mov     rsi, r8
0x1800191bf  mov     ebp, edx
0x1800191c1  mov     rbx, rcx
0x1800191c4  test    r8, r8
0x1800191c7  jnz     short loc_1800191D2
0x1800191c9  lea     eax, [r8+0Bh]
0x1800191cd  jmp     loc_180019257
0x1800191d2  test    edi, 0FFFFFFF8h
0x1800191d8  jz      short loc_1800191E1
0x1800191da  mov     eax, 0Ah
0x1800191df  jmp     short loc_180019257
0x1800191e1  call    ClientUpdatePnpInfo
0x1800191e6  mov     edx, 3
0x1800191eb  mov     rcx, rbx
0x1800191ee  call    ValidateHandle
0x1800191f3  test    eax, eax
0x1800191f5  jnz     short loc_18001920D
0x1800191f7  lea     edx, [rax+9]
0x1800191fa  mov     rcx, rbx
0x1800191fd  call    ValidateHandle
0x180019202  test    eax, eax
0x180019204  jnz     short loc_18001920D
0x180019206  mov     eax, 5
0x18001920b  jmp     short loc_180019257
0x18001920d  cmp     dword ptr [rbx-48h], 3
0x180019211  jz      short loc_180019239
0x180019213  cmp     dword ptr [rbx-48h], 9
0x180019217  jnz     short loc_180019206
0x180019219  movzx   ecx, bp
0x18001921c  mov     r8, rsi
0x18001921f  shl     ecx, 10h
0x180019222  mov     edx, 0Dh
0x180019227  movzx   eax, di
0x18001922a  or      ecx, eax
0x18001922c  movsxd  r9, ecx
0x18001922f  mov     rcx, rbx
0x180019232  call    midiStreamBroadcast
0x180019237  jmp     short loc_180019257
0x180019239  movzx   ecx, bp
0x18001923c  mov     r8, rsi
0x18001923f  shl     ecx, 10h
0x180019242  mov     edx, 0Dh
0x180019247  movzx   eax, di
0x18001924a  or      ecx, eax
0x18001924c  movsxd  r9, ecx
0x18001924f  mov     rcx, rbx
0x180019252  call    midiMessage
0x180019257  add     rsp, 28h
0x18001925b  pop     rdi
0x18001925c  pop     rsi
0x18001925d  pop     rbp
0x18001925e  pop     rbx
0x18001925f  retn
```
