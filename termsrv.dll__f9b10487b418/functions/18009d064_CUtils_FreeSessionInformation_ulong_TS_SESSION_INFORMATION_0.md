# CUtils::FreeSessionInformation(ulong,_TS_SESSION_INFORMATION_0 *)

- ea: `0x18009d064`
- end: `0x18009d0b8`
- name: `?FreeSessionInformation@CUtils@@SAXKPEAU_TS_SESSION_INFORMATION_0@@@Z`
- size: `84`
- prototype: `static void(unsigned int, struct _TS_SESSION_INFORMATION_0 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800744ec`
- `0x180077e94`

## callees

- `0x18009d064`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d08a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d09a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d0a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d08a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d09a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d0a9`

## pseudocode

```c
void __fastcall CUtils::FreeSessionInformation(unsigned int a1, struct _TS_SESSION_INFORMATION_0 *a2)
{
  __int64 i; // rdi
  void *v5; // rcx
  void *v6; // rcx

  if ( a2 )
  {
    for ( i = 0; (unsigned int)i < a1; i = (unsigned int)(i + 1) )
    {
      v5 = (void *)*((_QWORD *)a2 + 3 * i + 2);
      if ( v5 )
        CoTaskMemFree(v5);
      v6 = (void *)*((_QWORD *)a2 + 3 * i + 1);
      if ( v6 )
        CoTaskMemFree(v6);
    }
    CoTaskMemFree(a2);
  }
}

```

## disassembly

```asm
0x18009d064  test    rdx, rdx
0x18009d067  jz      short locret_18009D0B7
0x18009d069  push    rbx
0x18009d06a  push    rbp
0x18009d06b  push    rsi
0x18009d06c  push    rdi
0x18009d06d  sub     rsp, 28h
0x18009d071  xor     edi, edi
0x18009d073  mov     rbx, rdx
0x18009d076  mov     esi, ecx
0x18009d078  test    ecx, ecx
0x18009d07a  jz      short loc_18009D0A6
0x18009d07c  lea     rbp, [rdi+rdi*2]
0x18009d080  mov     rcx, [rbx+rbp*8+10h]; pv
0x18009d085  test    rcx, rcx
0x18009d088  jz      short loc_18009D090
0x18009d08a  call    cs:__imp_CoTaskMemFree
0x18009d090  mov     rcx, [rbx+rbp*8+8]; pv
0x18009d095  test    rcx, rcx
0x18009d098  jz      short loc_18009D0A0
0x18009d09a  call    cs:__imp_CoTaskMemFree
0x18009d0a0  inc     edi
0x18009d0a2  cmp     edi, esi
0x18009d0a4  jb      short loc_18009D07C
0x18009d0a6  mov     rcx, rbx; pv
0x18009d0a9  call    cs:__imp_CoTaskMemFree
0x18009d0af  add     rsp, 28h
0x18009d0b3  pop     rdi
0x18009d0b4  pop     rsi
0x18009d0b5  pop     rbp
0x18009d0b6  pop     rbx
0x18009d0b7  retn
```
