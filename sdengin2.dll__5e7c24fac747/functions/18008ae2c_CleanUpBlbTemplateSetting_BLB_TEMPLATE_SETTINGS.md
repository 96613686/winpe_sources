# CleanUpBlbTemplateSetting(_BLB_TEMPLATE_SETTINGS *)

- ea: `0x18008ae2c`
- end: `0x18008af37`
- name: `?CleanUpBlbTemplateSetting@@YAXPEAU_BLB_TEMPLATE_SETTINGS@@@Z`
- size: `267`
- prototype: `void __fastcall(struct _BLB_TEMPLATE_SETTINGS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18003ecac`

## callees

- `0x18008adcc`
- `0x18008ae2c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18008ae73`
- `ole32!CoTaskMemFree` at `0x18008ae80`
- `ole32!CoTaskMemFree` at `0x18008ae8e`
- `ole32!CoTaskMemFree` at `0x18008ae9c`
- `ole32!CoTaskMemFree` at `0x18008aeaa`
- `ole32!CoTaskMemFree` at `0x18008aeb8`
- `ole32!CoTaskMemFree` at `0x18008aec6`
- `ole32!CoTaskMemFree` at `0x18008aed4`
- `ole32!CoTaskMemFree` at `0x18008af09`
- `ole32!CoTaskMemFree` at `0x18008ae73`
- `ole32!CoTaskMemFree` at `0x18008ae80`
- `ole32!CoTaskMemFree` at `0x18008ae8e`
- `ole32!CoTaskMemFree` at `0x18008ae9c`
- `ole32!CoTaskMemFree` at `0x18008aeaa`
- `ole32!CoTaskMemFree` at `0x18008aeb8`
- `ole32!CoTaskMemFree` at `0x18008aec6`
- `ole32!CoTaskMemFree` at `0x18008aed4`
- `ole32!CoTaskMemFree` at `0x18008af09`

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
0x18008ae2c  test    rcx, rcx
0x18008ae2f  jz      locret_18008AF36
0x18008ae35  mov     [rsp+arg_0], rbx
0x18008ae3a  mov     [rsp+arg_8], rsi
0x18008ae3f  push    rdi
0x18008ae40  sub     rsp, 20h
0x18008ae44  mov     rax, [rcx+30h]
0x18008ae48  xor     esi, esi
0x18008ae4a  mov     rbx, rcx
0x18008ae4d  test    rax, rax
0x18008ae50  jz      short loc_18008AE70
0x18008ae52  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008ae56  inc     rcx
0x18008ae59  cmp     [rax+rcx*2], si
0x18008ae5d  jnz     short loc_18008AE56
0x18008ae5f  add     rcx, rcx
0x18008ae62  jz      short loc_18008AE70
0x18008ae64  mov     [rax], sil
0x18008ae67  inc     rax
0x18008ae6a  sub     rcx, 1
0x18008ae6e  jnz     short loc_18008AE64
0x18008ae70  mov     rcx, [rbx]; pv
0x18008ae73  call    cs:__imp_CoTaskMemFree
0x18008ae79  mov     rcx, [rbx+10h]; pv
0x18008ae7d  mov     [rbx], rsi
0x18008ae80  call    cs:__imp_CoTaskMemFree
0x18008ae86  mov     rcx, [rbx+28h]; pv
0x18008ae8a  mov     [rbx+10h], rsi
0x18008ae8e  call    cs:__imp_CoTaskMemFree
0x18008ae94  mov     rcx, [rbx+30h]; pv
0x18008ae98  mov     [rbx+28h], rsi
0x18008ae9c  call    cs:__imp_CoTaskMemFree
0x18008aea2  mov     rcx, [rbx+40h]; pv
0x18008aea6  mov     [rbx+30h], rsi
0x18008aeaa  call    cs:__imp_CoTaskMemFree
0x18008aeb0  mov     rcx, [rbx+58h]; pv
0x18008aeb4  mov     [rbx+40h], rsi
0x18008aeb8  call    cs:__imp_CoTaskMemFree
0x18008aebe  mov     rcx, [rbx+50h]; pv
0x18008aec2  mov     [rbx+58h], rsi
0x18008aec6  call    cs:__imp_CoTaskMemFree
0x18008aecc  mov     rcx, [rbx+60h]; pv
0x18008aed0  mov     [rbx+50h], rsi
0x18008aed4  call    cs:__imp_CoTaskMemFree
0x18008aeda  mov     [rbx+60h], rsi
0x18008aede  cmp     [rbx+20h], rsi
0x18008aee2  jz      short loc_18008AF13
0x18008aee4  mov     edi, esi
0x18008aee6  cmp     [rbx+18h], esi
0x18008aee9  jbe     short loc_18008AF05
0x18008aeeb  mov     eax, edi
0x18008aeed  lea     rcx, [rax+rax*2]
0x18008aef1  mov     rax, [rbx+20h]
0x18008aef5  lea     rcx, [rax+rcx*8]; struct _BLB_TARGET_SETTINGS *
0x18008aef9  call    ?CleanUpBlbTargetSetting@@YAXPEAU_BLB_TARGET_SETTINGS@@@Z; CleanUpBlbTargetSetting(_BLB_TARGET_SETTINGS *)
0x18008aefe  inc     edi
0x18008af00  cmp     edi, [rbx+18h]
0x18008af03  jb      short loc_18008AEEB
0x18008af05  mov     rcx, [rbx+20h]; pv
0x18008af09  call    cs:__imp_CoTaskMemFree
0x18008af0f  mov     [rbx+20h], rsi
0x18008af13  mov     [rbx+18h], esi
0x18008af16  mov     eax, 0A8h
0x18008af1b  mov     [rbx], sil
0x18008af1e  inc     rbx
0x18008af21  sub     rax, 1
0x18008af25  jnz     short loc_18008AF1B
0x18008af27  mov     rbx, [rsp+28h+arg_0]
0x18008af2c  mov     rsi, [rsp+28h+arg_8]
0x18008af31  add     rsp, 20h
0x18008af35  pop     rdi
0x18008af36  retn
```
