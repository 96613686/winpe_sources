# Free_SR_RP_PROP(_SR_RP_PROP *)

- ea: `0x14000d1a4`
- end: `0x14000d29d`
- name: `?Free_SR_RP_PROP@@YAXPEAU_SR_RP_PROP@@@Z`
- size: `249`
- prototype: `void __fastcall(struct _SR_RP_PROP *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1400047e4`
- `0x14000d688`

## callees

- `0x14000d168`
- `0x14000d1a4`
- `0x14000d2a4`
- `0x14000d2f0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14000d1be`
- `ole32!CoTaskMemFree` at `0x14000d1cc`
- `ole32!CoTaskMemFree` at `0x14000d1da`
- `ole32!CoTaskMemFree` at `0x14000d1e8`
- `ole32!CoTaskMemFree` at `0x14000d21f`
- `ole32!CoTaskMemFree` at `0x14000d268`
- `ole32!CoTaskMemFree` at `0x14000d1be`
- `ole32!CoTaskMemFree` at `0x14000d1cc`
- `ole32!CoTaskMemFree` at `0x14000d1da`
- `ole32!CoTaskMemFree` at `0x14000d1e8`
- `ole32!CoTaskMemFree` at `0x14000d21f`
- `ole32!CoTaskMemFree` at `0x14000d268`

## pseudocode

```c
void __fastcall Free_SR_RP_PROP(struct _SR_RP_PROP *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  unsigned int *v5; // rdi
  unsigned int i; // esi
  _QWORD *v7; // rdi
  unsigned int v8; // esi
  LPVOID *v9; // rcx

  if ( a1 )
  {
    CoTaskMemFree(*((LPVOID *)a1 + 5));
    v2 = (void *)*((_QWORD *)a1 + 8);
    *((_QWORD *)a1 + 5) = 0;
    CoTaskMemFree(v2);
    v3 = (void *)*((_QWORD *)a1 + 9);
    *((_QWORD *)a1 + 8) = 0;
    CoTaskMemFree(v3);
    v4 = (void *)*((_QWORD *)a1 + 10);
    *((_QWORD *)a1 + 9) = 0;
    CoTaskMemFree(v4);
    v5 = (unsigned int *)((char *)a1 + 88);
    *((_QWORD *)a1 + 10) = 0;
    if ( *((_QWORD *)a1 + 12) )
    {
      for ( i = 0; i < *v5; ++i )
        Free_SR_VOLUME_PROP((struct _SR_VOLUME_PROP *)(*((_QWORD *)a1 + 12) + 48LL * i));
      CoTaskMemFree(*((LPVOID *)a1 + 12));
      *((_QWORD *)a1 + 12) = 0;
    }
    *v5 = 0;
    v7 = (_QWORD *)((char *)a1 + 144);
    if ( *((_QWORD *)a1 + 18) )
    {
      v8 = 0;
      if ( *((_DWORD *)a1 + 34) )
      {
        do
          Free_SR_ENVIRONMENT_PROP((LPVOID *)(*v7 + 16LL * v8++));
        while ( v8 < *((_DWORD *)a1 + 34) );
        v9 = (LPVOID *)((char *)a1 + 144);
      }
      else
      {
        v9 = (LPVOID *)((char *)a1 + 144);
      }
      CoTaskMemFree(*v9);
      *v7 = 0;
    }
    *((_DWORD *)a1 + 34) = 0;
    Free_StringArray((unsigned int *)a1 + 26, (unsigned __int16 ***)a1 + 14);
    Free_StringArray((unsigned int *)a1 + 30, (unsigned __int16 ***)a1 + 16);
  }
}

```

## disassembly

```asm
0x14000d1a4  test    rcx, rcx
0x14000d1a7  jz      locret_14000D29C
0x14000d1ad  push    rbx
0x14000d1ae  push    rbp
0x14000d1af  push    rsi
0x14000d1b0  push    rdi
0x14000d1b1  sub     rsp, 28h
0x14000d1b5  mov     rbx, rcx
0x14000d1b8  xor     ebp, ebp
0x14000d1ba  mov     rcx, [rcx+28h]; pv
0x14000d1be  call    cs:__imp_CoTaskMemFree
0x14000d1c4  mov     rcx, [rbx+40h]; pv
0x14000d1c8  mov     [rbx+28h], rbp
0x14000d1cc  call    cs:__imp_CoTaskMemFree
0x14000d1d2  mov     rcx, [rbx+48h]; pv
0x14000d1d6  mov     [rbx+40h], rbp
0x14000d1da  call    cs:__imp_CoTaskMemFree
0x14000d1e0  mov     rcx, [rbx+50h]; pv
0x14000d1e4  mov     [rbx+48h], rbp
0x14000d1e8  call    cs:__imp_CoTaskMemFree
0x14000d1ee  lea     rdi, [rbx+58h]
0x14000d1f2  mov     [rbx+50h], rbp
0x14000d1f6  cmp     [rbx+60h], rbp
0x14000d1fa  jz      short loc_14000D229
0x14000d1fc  mov     esi, ebp
0x14000d1fe  cmp     [rdi], ebp
0x14000d200  jbe     short loc_14000D21B
0x14000d202  mov     eax, esi
0x14000d204  lea     rcx, [rax+rax*2]
0x14000d208  shl     rcx, 4
0x14000d20c  add     rcx, [rbx+60h]; struct _SR_VOLUME_PROP *
0x14000d210  call    ?Free_SR_VOLUME_PROP@@YAXPEAU_SR_VOLUME_PROP@@@Z; Free_SR_VOLUME_PROP(_SR_VOLUME_PROP *)
0x14000d215  inc     esi
0x14000d217  cmp     esi, [rdi]
0x14000d219  jb      short loc_14000D202
0x14000d21b  mov     rcx, [rbx+60h]; pv
0x14000d21f  call    cs:__imp_CoTaskMemFree
0x14000d225  mov     [rbx+60h], rbp
0x14000d229  mov     [rdi], ebp
0x14000d22b  lea     rdi, [rbx+90h]
0x14000d232  cmp     [rdi], rbp
0x14000d235  jz      short loc_14000D271
0x14000d237  mov     esi, ebp
0x14000d239  cmp     [rbx+88h], ebp
0x14000d23f  jbe     short loc_14000D262
0x14000d241  mov     ecx, esi
0x14000d243  shl     rcx, 4
0x14000d247  add     rcx, [rdi]; struct _SR_ENVIRONMENT_PROP *
0x14000d24a  call    ?Free_SR_ENVIRONMENT_PROP@@YAXPEAU_SR_ENVIRONMENT_PROP@@@Z; Free_SR_ENVIRONMENT_PROP(_SR_ENVIRONMENT_PROP *)
0x14000d24f  inc     esi
0x14000d251  cmp     esi, [rbx+88h]
0x14000d257  jb      short loc_14000D241
0x14000d259  lea     rcx, [rbx+90h]
0x14000d260  jmp     short loc_14000D265
0x14000d262  mov     rcx, rdi
0x14000d265  mov     rcx, [rcx]; pv
0x14000d268  call    cs:__imp_CoTaskMemFree
0x14000d26e  mov     [rdi], rbp
0x14000d271  lea     rdx, [rbx+70h]; unsigned __int16 ***
0x14000d275  mov     [rbx+88h], ebp
0x14000d27b  lea     rcx, [rbx+68h]; unsigned int *
0x14000d27f  call    ?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z; Free_StringArray(ulong *,ushort * * *)
0x14000d284  lea     rdx, [rbx+80h]; unsigned __int16 ***
0x14000d28b  lea     rcx, [rbx+78h]; unsigned int *
0x14000d28f  call    ?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z; Free_StringArray(ulong *,ushort * * *)
0x14000d294  add     rsp, 28h
0x14000d298  pop     rdi
0x14000d299  pop     rsi
0x14000d29a  pop     rbp
0x14000d29b  pop     rbx
0x14000d29c  retn
```
