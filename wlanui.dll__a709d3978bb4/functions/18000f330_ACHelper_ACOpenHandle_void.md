# ACHelper::ACOpenHandle(void)

- ea: `0x18000f330`
- end: `0x18000f368`
- name: `?ACOpenHandle@ACHelper@@QEAAKXZ`
- size: `56`
- prototype: `unsigned int __fastcall(PHANDLE phClientHandle)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f1b8`
- `0x18000f288`
- `0x18000f370`
- `0x18000fe78`
- `0x180010870`

## callees

- `0x18000f330`

## import_xrefs

- `wlanapi!WlanOpenHandle` at `0x18000f351`
- `wlanapi!WlanOpenHandle` at `0x18000f351`

## pseudocode

```c
DWORD __fastcall ACHelper::ACOpenHandle(PHANDLE phClientHandle)
{
  DWORD result; // eax
  DWORD pdwNegotiatedVersion; // [rsp+30h] [rbp+8h] BYREF

  result = 0;
  pdwNegotiatedVersion = 0;
  if ( !*((_DWORD *)phClientHandle + 2) )
  {
    result = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, phClientHandle);
    if ( !result )
      *((_DWORD *)phClientHandle + 2) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000f330  push    rbx
0x18000f332  sub     rsp, 20h
0x18000f336  xor     eax, eax
0x18000f338  mov     rbx, rcx
0x18000f33b  mov     [rsp+28h+pdwNegotiatedVersion], eax
0x18000f33f  cmp     [rcx+8], eax
0x18000f342  jnz     short loc_18000F362
0x18000f344  mov     r9, rcx; phClientHandle
0x18000f347  lea     r8, [rsp+28h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18000f34c  lea     ecx, [rax+2]; dwClientVersion
0x18000f34f  xor     edx, edx; pReserved
0x18000f351  call    cs:__imp_WlanOpenHandle
0x18000f357  test    eax, eax
0x18000f359  jnz     short loc_18000F362
0x18000f35b  mov     dword ptr [rbx+8], 1
0x18000f362  add     rsp, 20h
0x18000f366  pop     rbx
0x18000f367  retn
```
