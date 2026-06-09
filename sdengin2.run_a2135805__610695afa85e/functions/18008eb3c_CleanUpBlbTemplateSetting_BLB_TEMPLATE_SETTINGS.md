# CleanUpBlbTemplateSetting(_BLB_TEMPLATE_SETTINGS *)

- ea: `0x18008eb3c`
- end: `0x18008ec7e`
- name: `?CleanUpBlbTemplateSetting@@YAXPEAU_BLB_TEMPLATE_SETTINGS@@@Z`
- size: `322`
- prototype: `void __fastcall(struct _BLB_TEMPLATE_SETTINGS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180040404`

## callees

- `0x18008eac8`
- `0x18008eb3c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18008eb83`
- `ole32!CoTaskMemFree` at `0x18008eb96`
- `ole32!CoTaskMemFree` at `0x18008ebaa`
- `ole32!CoTaskMemFree` at `0x18008ebbe`
- `ole32!CoTaskMemFree` at `0x18008ebd2`
- `ole32!CoTaskMemFree` at `0x18008ebe6`
- `ole32!CoTaskMemFree` at `0x18008ebfa`
- `ole32!CoTaskMemFree` at `0x18008ec0e`
- `ole32!CoTaskMemFree` at `0x18008ec49`
- `ole32!CoTaskMemFree` at `0x18008eb83`
- `ole32!CoTaskMemFree` at `0x18008eb96`
- `ole32!CoTaskMemFree` at `0x18008ebaa`
- `ole32!CoTaskMemFree` at `0x18008ebbe`
- `ole32!CoTaskMemFree` at `0x18008ebd2`
- `ole32!CoTaskMemFree` at `0x18008ebe6`
- `ole32!CoTaskMemFree` at `0x18008ebfa`
- `ole32!CoTaskMemFree` at `0x18008ec0e`
- `ole32!CoTaskMemFree` at `0x18008ec49`

## pseudocode

```c
void __fastcall CleanUpBlbTemplateSetting(struct _BLB_TEMPLATE_SETTINGS *a1)
{
  _BYTE *v1; // rax
  struct _BLB_TEMPLATE_SETTINGS *v2; // rbx
  __int64 v3; // rcx
  __int64 i; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  unsigned int j; // edi
  __int64 v13; // rax

  if ( a1 )
  {
    v1 = (_BYTE *)*((_QWORD *)a1 + 6);
    v2 = a1;
    if ( v1 )
    {
      v3 = -1;
      do
        ++v3;
      while ( *(_WORD *)&v1[2 * v3] );
      for ( i = 2 * v3; i; --i )
        *v1++ = 0;
    }
    CoTaskMemFree(*(LPVOID *)v2);
    v5 = (void *)*((_QWORD *)v2 + 2);
    *(_QWORD *)v2 = 0;
    CoTaskMemFree(v5);
    v6 = (void *)*((_QWORD *)v2 + 5);
    *((_QWORD *)v2 + 2) = 0;
    CoTaskMemFree(v6);
    v7 = (void *)*((_QWORD *)v2 + 6);
    *((_QWORD *)v2 + 5) = 0;
    CoTaskMemFree(v7);
    v8 = (void *)*((_QWORD *)v2 + 8);
    *((_QWORD *)v2 + 6) = 0;
    CoTaskMemFree(v8);
    v9 = (void *)*((_QWORD *)v2 + 11);
    *((_QWORD *)v2 + 8) = 0;
    CoTaskMemFree(v9);
    v10 = (void *)*((_QWORD *)v2 + 10);
    *((_QWORD *)v2 + 11) = 0;
    CoTaskMemFree(v10);
    v11 = (void *)*((_QWORD *)v2 + 12);
    *((_QWORD *)v2 + 10) = 0;
    CoTaskMemFree(v11);
    *((_QWORD *)v2 + 12) = 0;
    if ( *((_QWORD *)v2 + 4) )
    {
      for ( j = 0; j < *((_DWORD *)v2 + 6); ++j )
        CleanUpBlbTargetSetting((struct _BLB_TARGET_SETTINGS *)(*((_QWORD *)v2 + 4) + 24LL * j));
      CoTaskMemFree(*((LPVOID *)v2 + 4));
      *((_QWORD *)v2 + 4) = 0;
    }
    *((_DWORD *)v2 + 6) = 0;
    v13 = 168;
    do
    {
      *(_BYTE *)v2 = 0;
      v2 = (struct _BLB_TEMPLATE_SETTINGS *)((char *)v2 + 1);
      --v13;
    }
    while ( v13 );
  }
}

```

## disassembly

```asm
0x18008eb3c  test    rcx, rcx
0x18008eb3f  jz      locret_18008EC7C
0x18008eb45  mov     [rsp+arg_0], rbx
0x18008eb4a  mov     [rsp+arg_8], rsi
0x18008eb4f  push    rdi
0x18008eb50  sub     rsp, 20h
0x18008eb54  mov     rax, [rcx+30h]
0x18008eb58  xor     esi, esi
0x18008eb5a  mov     rbx, rcx
0x18008eb5d  test    rax, rax
0x18008eb60  jz      short loc_18008EB80
0x18008eb62  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008eb66  inc     rcx
0x18008eb69  cmp     [rax+rcx*2], si
0x18008eb6d  jnz     short loc_18008EB66
0x18008eb6f  add     rcx, rcx
0x18008eb72  jz      short loc_18008EB80
0x18008eb74  mov     [rax], sil
0x18008eb77  inc     rax
0x18008eb7a  sub     rcx, 1
0x18008eb7e  jnz     short loc_18008EB74
0x18008eb80  mov     rcx, [rbx]; pv
0x18008eb83  call    cs:__imp_CoTaskMemFree
0x18008eb8a  nop     dword ptr [rax+rax+00h]
0x18008eb8f  mov     rcx, [rbx+10h]; pv
0x18008eb93  mov     [rbx], rsi
0x18008eb96  call    cs:__imp_CoTaskMemFree
0x18008eb9d  nop     dword ptr [rax+rax+00h]
0x18008eba2  mov     rcx, [rbx+28h]; pv
0x18008eba6  mov     [rbx+10h], rsi
0x18008ebaa  call    cs:__imp_CoTaskMemFree
0x18008ebb1  nop     dword ptr [rax+rax+00h]
0x18008ebb6  mov     rcx, [rbx+30h]; pv
0x18008ebba  mov     [rbx+28h], rsi
0x18008ebbe  call    cs:__imp_CoTaskMemFree
0x18008ebc5  nop     dword ptr [rax+rax+00h]
0x18008ebca  mov     rcx, [rbx+40h]; pv
0x18008ebce  mov     [rbx+30h], rsi
0x18008ebd2  call    cs:__imp_CoTaskMemFree
0x18008ebd9  nop     dword ptr [rax+rax+00h]
0x18008ebde  mov     rcx, [rbx+58h]; pv
0x18008ebe2  mov     [rbx+40h], rsi
0x18008ebe6  call    cs:__imp_CoTaskMemFree
0x18008ebed  nop     dword ptr [rax+rax+00h]
0x18008ebf2  mov     rcx, [rbx+50h]; pv
0x18008ebf6  mov     [rbx+58h], rsi
0x18008ebfa  call    cs:__imp_CoTaskMemFree
0x18008ec01  nop     dword ptr [rax+rax+00h]
0x18008ec06  mov     rcx, [rbx+60h]; pv
0x18008ec0a  mov     [rbx+50h], rsi
0x18008ec0e  call    cs:__imp_CoTaskMemFree
0x18008ec15  nop     dword ptr [rax+rax+00h]
0x18008ec1a  mov     [rbx+60h], rsi
0x18008ec1e  cmp     [rbx+20h], rsi
0x18008ec22  jz      short loc_18008EC59
0x18008ec24  mov     edi, esi
0x18008ec26  cmp     [rbx+18h], esi
0x18008ec29  jbe     short loc_18008EC45
0x18008ec2b  mov     eax, edi
0x18008ec2d  lea     rcx, [rax+rax*2]
0x18008ec31  mov     rax, [rbx+20h]
0x18008ec35  lea     rcx, [rax+rcx*8]; struct _BLB_TARGET_SETTINGS *
0x18008ec39  call    ?CleanUpBlbTargetSetting@@YAXPEAU_BLB_TARGET_SETTINGS@@@Z; CleanUpBlbTargetSetting(_BLB_TARGET_SETTINGS *)
0x18008ec3e  inc     edi
0x18008ec40  cmp     edi, [rbx+18h]
0x18008ec43  jb      short loc_18008EC2B
0x18008ec45  mov     rcx, [rbx+20h]; pv
0x18008ec49  call    cs:__imp_CoTaskMemFree
0x18008ec50  nop     dword ptr [rax+rax+00h]
0x18008ec55  mov     [rbx+20h], rsi
0x18008ec59  mov     [rbx+18h], esi
0x18008ec5c  mov     eax, 0A8h
0x18008ec61  mov     [rbx], sil
0x18008ec64  inc     rbx
0x18008ec67  sub     rax, 1
0x18008ec6b  jnz     short loc_18008EC61
0x18008ec6d  mov     rbx, [rsp+28h+arg_0]
0x18008ec72  mov     rsi, [rsp+28h+arg_8]
0x18008ec77  add     rsp, 20h
0x18008ec7b  pop     rdi
0x18008ec7c  retn
```
