# SkmiUpdateEndpointWrapperSectionCount

- ea: `0x140082268`
- end: `0x14008239e`
- name: `SkmiUpdateEndpointWrapperSectionCount`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400812f8`

## callees

- `0x14000f0f0`
- `0x140025c58`
- `0x140037e68`
- `0x14007b5a8`
- `0x14008129c`
- `0x1400812bc`
- `0x1400817f0`
- `0x140082268`
- `0x1400a8cf0`
- `0x1400a9480`
- `0x1400f9780`

## pseudocode

```c
__int64 __fastcall SkmiUpdateEndpointWrapperSectionCount(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rbx
  int v4; // r8d
  unsigned int v5; // r15d
  int v6; // eax
  _DWORD *v7; // r14
  unsigned int v8; // edi
  int v9; // eax
  _DWORD *v10; // rsi
  unsigned int v11; // r15d
  _DWORD *Pool; // rax
  __int64 v13; // rdx
  __int64 v15; // [rsp+60h] [rbp+8h] BYREF
  void *Src; // [rsp+68h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 192);
  v2 = 0;
  v4 = *(_DWORD *)(a1 + 136) + *(_DWORD *)(a1 + 72);
  Src = 0;
  v5 = *(_DWORD *)(v1 + 56);
  v15 = 0;
  v6 = SkmiMapNormalKernelImageRange(a1, 4, v4, 2, (__int64)&Src);
  v7 = Src;
  v8 = v6;
  if ( v6 >= 0 )
  {
    v9 = SkmiCreateDriverProxyHyperguardContext(a1, &v15);
    v2 = v15;
    v8 = v9;
    if ( v9 >= 0 )
    {
      v10 = 0;
      v11 = v5 >> 1;
      if ( v15 )
      {
        Pool = (_DWORD *)SkAllocatePool(512, 0x1000u);
        v10 = Pool;
        if ( !Pool )
        {
          v8 = -1073741670;
          goto LABEL_9;
        }
        memmove(Pool, v7, 0x1000u);
        v10[7] = v11;
        SkpgHotpatchPrepare(
          v2,
          *(_QWORD *)(a1 + 24) + ((unsigned __int64)(unsigned int)(*(_DWORD *)(a1 + 136) + *(_DWORD *)(a1 + 72)) << 12),
          v10);
      }
      LOBYTE(v13) = SkmiApplyDriverProxyHyperguardContextEnter(v2);
      v7[7] = v11;
      SkmiApplyDriverProxyHyperguardContextExit(v2, v13);
      if ( v10 )
        SkFreePool(512, v10);
    }
  }
LABEL_9:
  if ( v7 )
    SkmiUnmapNormalKernelImageRange(v7, 2, 1);
  if ( v2 )
    SkpgHotpatchDestroy(v2);
  return v8;
}

```

## disassembly

```asm
0x140082268  mov     r11, rsp
0x14008226b  mov     [r11+18h], rbx
0x14008226f  push    rbp
0x140082270  push    rsi
0x140082271  push    rdi
0x140082272  push    r14
0x140082274  push    r15
0x140082276  sub     rsp, 30h
0x14008227a  mov     rax, [rcx+0C0h]
0x140082281  xor     ebx, ebx
0x140082283  mov     r8d, [rcx+48h]
0x140082287  mov     rbp, rcx
0x14008228a  add     r8d, [rcx+88h]
0x140082291  mov     qword ptr [r11+10h], 0
0x140082299  mov     r15d, [rax+38h]
0x14008229d  lea     edx, [rbx+4]
0x1400822a0  lea     rax, [r11+10h]
0x1400822a4  mov     [r11+8], rbx
0x1400822a8  lea     r9d, [rbx+2]
0x1400822ac  mov     [r11-38h], rax
0x1400822b0  call    SkmiMapNormalKernelImageRange
0x1400822b5  mov     r14, [rsp+58h+Src]
0x1400822ba  mov     edi, eax
0x1400822bc  test    eax, eax
0x1400822be  js      loc_140082367
0x1400822c4  lea     rdx, [rsp+58h+arg_0]
0x1400822c9  mov     rcx, rbp
0x1400822cc  call    SkmiCreateDriverProxyHyperguardContext
0x1400822d1  mov     rbx, [rsp+58h+arg_0]
0x1400822d6  mov     edi, eax
0x1400822d8  test    eax, eax
0x1400822da  js      loc_140082367
0x1400822e0  xor     esi, esi
0x1400822e2  shr     r15d, 1
0x1400822e5  test    rbx, rbx
0x1400822e8  jz      short loc_14008233F
0x1400822ea  mov     edx, 1000h
0x1400822ef  mov     ecx, 200h
0x1400822f4  mov     r8d, 78727044h
0x1400822fa  call    SkAllocatePool
0x1400822ff  mov     rsi, rax
0x140082302  test    rax, rax
0x140082305  jnz     short loc_14008230E
0x140082307  mov     edi, 0C000009Ah
0x14008230c  jmp     short loc_140082367
0x14008230e  mov     r8d, 1000h; Size
0x140082314  mov     rdx, r14; Src
0x140082317  mov     rcx, rsi; void *
0x14008231a  call    memmove
0x14008231f  mov     [rsi+1Ch], r15d
0x140082323  mov     r8, rsi
0x140082326  mov     edx, [rbp+48h]
0x140082329  mov     rcx, rbx
0x14008232c  add     edx, [rbp+88h]
0x140082332  shl     rdx, 0Ch
0x140082336  add     rdx, [rbp+18h]
0x14008233a  call    SkpgHotpatchPrepare
0x14008233f  mov     rcx, rbx
0x140082342  call    SkmiApplyDriverProxyHyperguardContextEnter
0x140082347  mov     dl, al
0x140082349  mov     [r14+1Ch], r15d
0x14008234d  mov     rcx, rbx
0x140082350  call    SkmiApplyDriverProxyHyperguardContextExit
0x140082355  test    rsi, rsi
0x140082358  jz      short loc_140082367
0x14008235a  mov     rdx, rsi
0x14008235d  mov     ecx, 200h
0x140082362  call    SkFreePool
0x140082367  test    r14, r14
0x14008236a  jz      short loc_14008237D
0x14008236c  mov     edx, 2
0x140082371  mov     rcx, r14
0x140082374  lea     r8d, [rdx-1]
0x140082378  call    SkmiUnmapNormalKernelImageRange
0x14008237d  test    rbx, rbx
0x140082380  jz      short loc_14008238A
0x140082382  mov     rcx, rbx
0x140082385  call    SkpgHotpatchDestroy
0x14008238a  mov     rbx, [rsp+58h+arg_10]
0x14008238f  mov     eax, edi
0x140082391  add     rsp, 30h
0x140082395  pop     r15
0x140082397  pop     r14
0x140082399  pop     rdi
0x14008239a  pop     rsi
0x14008239b  pop     rbp
0x14008239c  retn
```
