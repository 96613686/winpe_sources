# Free_SPP_ONDISK_VOLUME_PROP(_SPP_ONDISK_VOLUME_PROP *)

- ea: `0x180008ffc`
- end: `0x180009073`
- name: `?Free_SPP_ONDISK_VOLUME_PROP@@YAXPEAU_SPP_ONDISK_VOLUME_PROP@@@Z`
- size: `119`
- prototype: `void __fastcall(LPVOID *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800026ac`
- `0x180008ed0`
- `0x18001212c`

## callees

- `0x180008ffc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000900c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000903a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009056`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000900c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000903a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009056`

## pseudocode

```c
void __fastcall Free_SPP_ONDISK_VOLUME_PROP(LPVOID *a1)
{
  LPVOID *v2; // rsi
  __int64 i; // rbp

  CoTaskMemFree(a1[3]);
  a1[3] = 0;
  v2 = a1 + 4;
  *((_DWORD *)a1 + 4) = 0;
  if ( a1[5] )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)v2; i = (unsigned int)(i + 1) )
    {
      CoTaskMemFree(*((LPVOID *)a1[5] + i));
      *((_QWORD *)a1[5] + i) = 0;
    }
    CoTaskMemFree(a1[5]);
    a1[5] = 0;
  }
  *(_DWORD *)v2 = 0;
}

```

## disassembly

```asm
0x180008ffc  push    rbx
0x180008ffe  push    rbp
0x180008fff  push    rsi
0x180009000  push    rdi
0x180009001  sub     rsp, 28h
0x180009005  mov     rdi, rcx
0x180009008  mov     rcx, [rcx+18h]; pv
0x18000900c  call    cs:__imp_CoTaskMemFree
0x180009012  mov     qword ptr [rdi+18h], 0
0x18000901a  lea     rsi, [rdi+20h]
0x18000901e  mov     dword ptr [rdi+10h], 0
0x180009025  cmp     qword ptr [rdi+28h], 0
0x18000902a  jz      short loc_180009064
0x18000902c  xor     ebp, ebp
0x18000902e  cmp     [rsi], ebp
0x180009030  jbe     short loc_180009052
0x180009032  mov     rcx, [rdi+28h]
0x180009036  mov     rcx, [rcx+rbp*8]; pv
0x18000903a  call    cs:__imp_CoTaskMemFree
0x180009040  mov     rax, [rdi+28h]
0x180009044  mov     qword ptr [rax+rbp*8], 0
0x18000904c  inc     ebp
0x18000904e  cmp     ebp, [rsi]
0x180009050  jb      short loc_180009032
0x180009052  mov     rcx, [rdi+28h]; pv
0x180009056  call    cs:__imp_CoTaskMemFree
0x18000905c  mov     qword ptr [rdi+28h], 0
0x180009064  mov     dword ptr [rsi], 0
0x18000906a  add     rsp, 28h
0x18000906e  pop     rdi
0x18000906f  pop     rsi
0x180009070  pop     rbp
0x180009071  pop     rbx
0x180009072  retn
```
