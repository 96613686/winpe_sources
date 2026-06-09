# UdfMakeCompatible

- ea: `0x1400361d8`
- end: `0x1400362d9`
- name: `UdfMakeCompatible`
- size: `257`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14004b594`

## callees

- `0x1400030e0`
- `0x140013e10`
- `0x1400361d8`
- `0x14003aa44`
- `0x1400444c4`
- `0x14004ce50`
- `0x140054460`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14003629d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003629d`

## pseudocode

```c
__int64 __fastcall UdfMakeCompatible(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rdi
  __int64 v5; // r11
  struct _ERESOURCE *v6; // rsi
  __int64 v7; // r8
  unsigned int v8; // edi
  unsigned int Compatible; // eax
  __int64 v10; // rdx
  _DWORD *v12; // [rsp+40h] [rbp+8h] BYREF
  __int64 v13; // [rsp+48h] [rbp+10h] BYREF

  v4 = *(_DWORD **)(a1 + 16);
  if ( (unsigned int)UdfDecodeFileObject(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 48LL), &v13, &v12) == 2
    && *(_DWORD *)(v5 + 16) )
  {
    v12 = v4;
    *(_DWORD *)(a1 + 28) |= 4u;
    v6 = (struct _ERESOURCE *)(v4 + 370);
    UdfAcquireResource(a1, v4 + 370, 0, 0);
    UdfVerifyVcb(a1, v4, v7);
    if ( (v4[12] & 0x204010) == 0x200000 && (v4[21] & 0x10) != 0 )
    {
      if ( (v4[532] & 0x80u) == 0 )
      {
        if ( (v4[12] & 0x20000000) != 0 )
          Compatible = UdfPowMakeCompatible(a1);
        else
          Compatible = UdfSeqCacheCloseSession(a1);
        v8 = Compatible;
      }
      else
      {
        v8 = 0;
      }
    }
    else
    {
      v8 = -1073741808;
    }
    ExReleaseResourceLite(v6);
    v10 = a2;
  }
  else
  {
    v8 = -1073741811;
    v10 = *(_QWORD *)(a1 + 8);
  }
  UdfCompleteRequest(a1, v10, v8);
  return v8;
}

```

## disassembly

```asm
0x1400361d8  mov     rax, rsp
0x1400361db  mov     [rax+18h], rbx
0x1400361df  mov     [rax+20h], rsi
0x1400361e3  push    rdi
0x1400361e4  push    r14
0x1400361e6  push    r15
0x1400361e8  sub     rsp, 20h
0x1400361ec  mov     r14, rdx
0x1400361ef  mov     rbx, rcx
0x1400361f2  mov     r11, [rdx+0B8h]
0x1400361f9  mov     r15, [rdx+18h]
0x1400361fd  mov     rdi, [rcx+10h]
0x140036201  lea     r8, [rax+8]
0x140036205  lea     rdx, [rax+10h]
0x140036209  mov     rcx, [r11+30h]
0x14003620d  call    UdfDecodeFileObject
0x140036212  cmp     eax, 2
0x140036215  jnz     loc_1400362AE
0x14003621b  cmp     dword ptr [r11+10h], 1
0x140036220  jb      loc_1400362AE
0x140036226  mov     [rsp+38h+arg_0], rdi
0x14003622b  or      dword ptr [rbx+1Ch], 4
0x14003622f  lea     rsi, [rdi+5C8h]
0x140036236  xor     r9d, r9d
0x140036239  xor     r8d, r8d
0x14003623c  mov     rdx, rsi
0x14003623f  mov     rcx, rbx
0x140036242  call    UdfAcquireResource
0x140036247  nop
0x140036248  mov     rdx, rdi
0x14003624b  mov     rcx, rbx
0x14003624e  call    UdfVerifyVcb
0x140036253  mov     ecx, [rdi+30h]
0x140036256  mov     eax, ecx
0x140036258  and     eax, 204010h
0x14003625d  cmp     eax, 200000h
0x140036262  jnz     short loc_140036295
0x140036264  mov     eax, [rdi+54h]
0x140036267  test    al, 10h
0x140036269  jz      short loc_140036295
0x14003626b  mov     eax, [rdi+850h]
0x140036271  test    al, al
0x140036273  jns     short loc_140036279
0x140036275  xor     edi, edi
0x140036277  jmp     short loc_14003629A
0x140036279  bt      ecx, 1Dh
0x14003627d  mov     rcx, rbx
0x140036280  jnb     short loc_14003628B
0x140036282  call    UdfPowMakeCompatible
0x140036287  mov     edi, eax
0x140036289  jmp     short loc_14003629A
0x14003628b  mov     dl, [r15]
0x14003628e  call    UdfSeqCacheCloseSession
0x140036293  jmp     short loc_140036287
0x140036295  mov     edi, 0C0000010h
0x14003629a  mov     rcx, rsi; Resource
0x14003629d  call    cs:__imp_ExReleaseResourceLite
0x1400362a4  nop     dword ptr [rax+rax+00h]
0x1400362a9  mov     rdx, r14
0x1400362ac  jmp     short loc_1400362B7
0x1400362ae  mov     edi, 0C000000Dh
0x1400362b3  mov     rdx, [rbx+8]
0x1400362b7  mov     r8d, edi
0x1400362ba  mov     rcx, rbx
0x1400362bd  call    UdfCompleteRequest
0x1400362c2  mov     eax, edi
0x1400362c4  mov     rbx, [rsp+38h+arg_10]
0x1400362c9  mov     rsi, [rsp+38h+arg_18]
0x1400362ce  add     rsp, 20h
0x1400362d2  pop     r15
0x1400362d4  pop     r14
0x1400362d6  pop     rdi
0x1400362d7  retn
0x14005bef4  push    rbp
0x14005bef6  sub     rsp, 20h
0x14005befa  mov     rbp, rdx
0x14005befd  mov     rcx, [rbp+40h]
0x14005bf01  add     rcx, 5C8h; Resource
0x14005bf08  call    cs:__imp_ExReleaseResourceLite
0x14005bf0f  nop     dword ptr [rax+rax+00h]
0x14005bf14  nop
0x14005bf15  add     rsp, 20h
0x14005bf19  pop     rbp
0x14005bf1a  retn
```
