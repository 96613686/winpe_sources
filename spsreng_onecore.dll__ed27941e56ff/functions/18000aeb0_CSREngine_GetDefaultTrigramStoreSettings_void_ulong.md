# CSREngine::GetDefaultTrigramStoreSettings(void * *,ulong *)

- ea: `0x18000aeb0`
- end: `0x18000af5e`
- name: `?GetDefaultTrigramStoreSettings@CSREngine@@AEAAJPEAPEAXPEAK@Z`
- size: `174`
- prototype: `__int64 __fastcall(CSREngine *__hidden this, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ed20`

## callees

- `0x18000aeb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aee6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aee6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSREngine::GetDefaultTrigramStoreSettings(CSREngine *this, void **a2, unsigned int *a3)
{
  __int64 result; // rax
  void *v7; // rax
  __int64 v8; // rax
  _OWORD *v9; // rcx
  __int128 v10; // xmm1

  result = 2147500037LL;
  if ( *((_QWORD *)this + 17) && a2 && a3 )
  {
    v7 = CoTaskMemAlloc(0x60u);
    *a2 = v7;
    if ( v7 )
    {
      *a3 = 96;
      v8 = *((_QWORD *)this + 17);
      v9 = *a2;
      *v9 = *(_OWORD *)(v8 + 520);
      v9[1] = *(_OWORD *)(v8 + 536);
      v9[2] = *(_OWORD *)(v8 + 552);
      v9[3] = *(_OWORD *)(v8 + 568);
      v9[4] = *(_OWORD *)(v8 + 584);
      v10 = *(_OWORD *)(v8 + 600);
      result = 0;
      v9[5] = v10;
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000aeb0  mov     [rsp+arg_0], rbx
0x18000aeb5  mov     [rsp+arg_8], rsi
0x18000aeba  push    rdi
0x18000aebb  sub     rsp, 20h
0x18000aebf  cmp     qword ptr [rcx+88h], 0
0x18000aec7  mov     rdi, r8
0x18000aeca  mov     rbx, rdx
0x18000aecd  mov     rsi, rcx
0x18000aed0  mov     eax, 80004005h
0x18000aed5  jz      short loc_18000AF4E
0x18000aed7  test    rdx, rdx
0x18000aeda  jz      short loc_18000AF4E
0x18000aedc  test    r8, r8
0x18000aedf  jz      short loc_18000AF4E
0x18000aee1  mov     ecx, 60h ; '`'; cb
0x18000aee6  call    cs:__imp_CoTaskMemAlloc
0x18000aeec  mov     [rbx], rax
0x18000aeef  test    rax, rax
0x18000aef2  jz      short loc_18000AF49
0x18000aef4  mov     dword ptr [rdi], 60h ; '`'
0x18000aefa  mov     rax, [rsi+88h]
0x18000af01  mov     rcx, [rbx]
0x18000af04  movups  xmm0, xmmword ptr [rax+208h]
0x18000af0b  movups  xmmword ptr [rcx], xmm0
0x18000af0e  movups  xmm1, xmmword ptr [rax+218h]
0x18000af15  movups  xmmword ptr [rcx+10h], xmm1
0x18000af19  movups  xmm0, xmmword ptr [rax+228h]
0x18000af20  movups  xmmword ptr [rcx+20h], xmm0
0x18000af24  movups  xmm1, xmmword ptr [rax+238h]
0x18000af2b  movups  xmmword ptr [rcx+30h], xmm1
0x18000af2f  movups  xmm0, xmmword ptr [rax+248h]
0x18000af36  movups  xmmword ptr [rcx+40h], xmm0
0x18000af3a  movups  xmm1, xmmword ptr [rax+258h]
0x18000af41  xor     eax, eax
0x18000af43  movups  xmmword ptr [rcx+50h], xmm1
0x18000af47  jmp     short loc_18000AF4E
0x18000af49  mov     eax, 8007000Eh
0x18000af4e  mov     rbx, [rsp+28h+arg_0]
0x18000af53  mov     rsi, [rsp+28h+arg_8]
0x18000af58  add     rsp, 20h
0x18000af5c  pop     rdi
0x18000af5d  retn
```
