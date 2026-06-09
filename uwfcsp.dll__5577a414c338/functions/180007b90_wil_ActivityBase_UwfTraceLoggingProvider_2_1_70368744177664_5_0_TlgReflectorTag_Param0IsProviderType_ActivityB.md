# wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)

- ea: `0x180007b90`
- end: `0x180007c51`
- name: `??0?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z`
- size: `193`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180008ee0`
- `0x1800091c0`
- `0x18000d2d0`
- `0x18000dcb0`
- `0x18000e300`
- `0x18000e610`
- `0x18000e9f0`
- `0x18000ed30`
- `0x18000f340`
- `0x18000f8a0`

## callees

- `0x18001a1d6`

## string_xrefs

- `0x180007bbc`: `ConfigurationActivity`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  __int64 v1; // rbx
  _QWORD *v3; // rcx
  __int64 result; // rax

  v1 = a1 + 8;
  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = &wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v3 = (_QWORD *)(a1 + 88);
  *(_BYTE *)(v1 + 4) = 0;
  v3[19] = 0;
  *(_QWORD *)(v1 + 48) = "ConfigurationActivity";
  v3[20] = 0;
  *(_BYTE *)(v1 + 64) = 0;
  *(_DWORD *)(v1 + 40) = 0;
  *(_QWORD *)(v1 + 56) = 0;
  *(_DWORD *)(v1 + 72) = 0;
  memset_0(v3, 0, 0x98u);
  *(_DWORD *)(v1 + 248) = 1;
  *(_QWORD *)(v1 + 256) = 0;
  *(_QWORD *)(a1 + 272) = v1;
  *(_QWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 320) = a1 + 48;
  result = a1;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 304) = 0;
  *(_DWORD *)(a1 + 312) = 0;
  *(_BYTE *)(a1 + 328) = 0;
  *(_QWORD *)(a1 + 296) = a1;
  return result;
}

```

## disassembly

```asm
0x180007b90  mov     [rsp+arg_0], rbx
0x180007b95  mov     [rsp+arg_8], rsi
0x180007b9a  push    rdi
0x180007b9b  sub     rsp, 20h
0x180007b9f  lea     rbx, [rcx+8]
0x180007ba3  xor     esi, esi
0x180007ba5  lea     rax, ??_7?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x180007bac  mov     [rbx], esi
0x180007bae  mov     [rcx], rax
0x180007bb1  mov     rdi, rcx
0x180007bb4  lea     rcx, [rbx+50h]; void *
0x180007bb8  mov     [rbx+4], sil
0x180007bbc  lea     rax, aConfigurationa; "ConfigurationActivity"
0x180007bc3  mov     [rcx+98h], rsi
0x180007bca  xor     edx, edx; Val
0x180007bcc  mov     [rbx+30h], rax
0x180007bd0  mov     r8d, 98h; Size
0x180007bd6  mov     [rcx+0A0h], rsi
0x180007bdd  mov     [rbx+40h], sil
0x180007be1  mov     [rbx+28h], esi
0x180007be4  mov     [rbx+38h], rsi
0x180007be8  mov     [rbx+48h], esi
0x180007beb  call    memset_0
0x180007bf0  mov     dword ptr [rbx+0F8h], 1
0x180007bfa  xor     eax, eax
0x180007bfc  mov     [rbx+100h], rax
0x180007c03  lea     rax, [rdi+30h]
0x180007c07  mov     [rdi+110h], rbx
0x180007c0e  mov     rbx, [rsp+28h+arg_0]
0x180007c13  mov     [rdi+118h], rsi
0x180007c1a  mov     [rdi+140h], rax
0x180007c21  mov     rax, rdi
0x180007c24  mov     [rdi+120h], rsi
0x180007c2b  mov     [rdi+130h], rsi
0x180007c32  mov     [rdi+138h], esi
0x180007c38  mov     [rdi+148h], sil
0x180007c3f  mov     rsi, [rsp+28h+arg_8]
0x180007c44  mov     [rdi+128h], rdi
0x180007c4b  add     rsp, 20h
0x180007c4f  pop     rdi
0x180007c50  retn
```
