# WriteRegDataBuffer(REGISTRY_SCAN_FUNC_ARGS *)

- ea: `0x180025274`
- end: `0x180025382`
- name: `?WriteRegDataBuffer@@YAXPEAUREGISTRY_SCAN_FUNC_ARGS@@@Z`
- size: `270`
- prototype: `void __fastcall(struct REGISTRY_SCAN_FUNC_ARGS *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800245a0`
- `0x180024938`

## callees

- `0x1800010b0`
- `0x180002d9c`
- `0x180005c94`
- `0x180025274`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002533a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002533a`

## pseudocode

```c
void __fastcall WriteRegDataBuffer(struct REGISTRY_SCAN_FUNC_ARGS *a1)
{
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  void *v5; // rcx
  __int64 v6; // [rsp+50h] [rbp-20h] BYREF
  __int16 v7; // [rsp+58h] [rbp-18h]
  __int64 v8; // [rsp+60h] [rbp-10h] BYREF
  __int16 v9; // [rsp+68h] [rbp-8h]
  __int16 v10; // [rsp+90h] [rbp+20h] BYREF
  int v11; // [rsp+98h] [rbp+28h] BYREF
  char *v12; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v13; // [rsp+A8h] [rbp+38h] BYREF

  if ( *((_WORD *)a1 + 4) )
  {
    if ( (unsigned int)dword_180040010 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
      {
        v10 = *((_WORD *)a1 + 2);
        v12 = (char *)a1 + 32;
        v6 = *((_QWORD *)a1 + 3);
        v8 = *((_QWORD *)a1 + 2);
        v11 = *(_DWORD *)a1;
        v7 = v3;
        v9 = v3;
        v13 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperArray<4>,_tlgWrapperArray<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<2>>(
          v2,
          (unsigned int)&byte_1800384C7,
          v3,
          v4,
          (__int64)&v13,
          (__int64)&v11,
          (__int64)&v8,
          (__int64)&v6,
          (__int64)&v12,
          (__int64)&v10);
      }
    }
    Sleep(0x28u);
    v5 = (void *)*((_QWORD *)a1 + 3);
    *((_WORD *)a1 + 4) = 0;
    memset_0(v5, 0, 0x320u);
    memset_0(*((void **)a1 + 2), 0, 0x320u);
    memset_0(*((void **)a1 + 5), 0, *((unsigned __int16 *)a1 + 17));
    *((_WORD *)a1 + 2) = 0;
  }
}

```

## disassembly

```asm
0x180025274  push    rbp
0x180025276  push    rbx
0x180025277  push    rsi
0x180025278  mov     rbp, rsp
0x18002527b  sub     rsp, 70h
0x18002527f  movzx   r8d, word ptr [rcx+8]
0x180025284  xor     esi, esi
0x180025286  mov     rbx, rcx
0x180025289  test    r8w, r8w
0x18002528d  jz      loc_18002537A
0x180025293  mov     eax, cs:dword_180040010
0x180025299  cmp     eax, 5
0x18002529c  jbe     loc_180025335
0x1800252a2  mov     rdx, 400000000000h
0x1800252ac  lea     rcx, dword_180040010
0x1800252b3  call    _tlgKeywordOn
0x1800252b8  test    al, al
0x1800252ba  jz      short loc_180025335
0x1800252bc  movzx   eax, word ptr [rbx+4]
0x1800252c0  lea     rdx, byte_1800384C7
0x1800252c7  mov     [rbp+arg_0], ax
0x1800252cb  lea     rax, [rbx+20h]
0x1800252cf  mov     [rbp+arg_10], rax
0x1800252d3  mov     rax, [rbx+18h]
0x1800252d7  mov     [rbp+var_20], rax
0x1800252db  mov     rax, [rbx+10h]
0x1800252df  mov     [rbp+var_10], rax
0x1800252e3  mov     eax, [rbx]
0x1800252e5  mov     [rbp+arg_8], eax
0x1800252e8  lea     rax, [rbp+arg_0]
0x1800252ec  mov     [rsp+70h+var_28], rax
0x1800252f1  lea     rax, [rbp+arg_10]
0x1800252f5  mov     [rsp+70h+var_30], rax
0x1800252fa  lea     rax, [rbp+var_20]
0x1800252fe  mov     [rsp+70h+var_38], rax
0x180025303  lea     rax, [rbp+var_10]
0x180025307  mov     [rsp+70h+var_40], rax
0x18002530c  lea     rax, [rbp+arg_8]
0x180025310  mov     [rsp+70h+var_48], rax
0x180025315  lea     rax, [rbp+arg_18]
0x180025319  mov     [rsp+70h+var_50], rax
0x18002531e  mov     [rbp+var_18], r8w
0x180025323  mov     [rbp+var_8], r8w
0x180025328  mov     [rbp+arg_18], 1000000h
0x180025330  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperArray@$03@@U3@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperArray@$03@@5AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperArray<4>,_tlgWrapperArray<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<4> const &,_tlgWrapperArray<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<2> const &)
0x180025335  mov     ecx, 28h ; '('; dwMilliseconds
0x18002533a  call    cs:__imp_Sleep
0x180025340  mov     rcx, [rbx+18h]; void *
0x180025344  xor     edx, edx; Val
0x180025346  mov     r8d, 320h; Size
0x18002534c  mov     [rbx+8], si
0x180025350  call    memset_0
0x180025355  mov     rcx, [rbx+10h]; void *
0x180025359  xor     edx, edx; Val
0x18002535b  mov     r8d, 320h; Size
0x180025361  call    memset_0
0x180025366  movzx   r8d, word ptr [rbx+22h]; Size
0x18002536b  xor     edx, edx; Val
0x18002536d  mov     rcx, [rbx+28h]; void *
0x180025371  call    memset_0
0x180025376  mov     [rbx+4], si
0x18002537a  add     rsp, 70h
0x18002537e  pop     rsi
0x18002537f  pop     rbx
0x180025380  pop     rbp
0x180025381  retn
```
