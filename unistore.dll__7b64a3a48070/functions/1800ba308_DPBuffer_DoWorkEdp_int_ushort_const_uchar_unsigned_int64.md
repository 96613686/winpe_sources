# DPBuffer::_DoWorkEdp(int,ushort const *,uchar *,unsigned __int64)

- ea: `0x1800ba308`
- end: `0x1800ba3e8`
- name: `?_DoWorkEdp@DPBuffer@@AEAAJHPEBGPEAE_K@Z`
- size: `224`
- prototype: `__int64 __fastcall(DPBuffer *__hidden this, int, const unsigned __int16 *, unsigned __int8 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180069ebc`
- `0x1800ba138`

## callees

- `0x18006e0f0`
- `0x1800ba084`
- `0x1800ba308`

## import_xrefs

- `efswrt!DpmStreamClose` at `0x1800ba36f`
- `efswrt!DpmStreamClose` at `0x1800ba3d7`
- `efswrt!DpmStreamClose` at `0x1800ba36f`
- `efswrt!DpmStreamClose` at `0x1800ba3d7`
- `efswrt!DpmStreamUpdate` at `0x1800ba3b2`
- `efswrt!DpmStreamUpdate` at `0x1800ba3b2`
- `efswrt!DpmStreamOpenToUnprotect` at `0x1800ba38b`
- `efswrt!DpmStreamOpenToUnprotect` at `0x1800ba38b`
- `efswrt!DpmStreamOpenToProtectToIdentity` at `0x1800ba34a`
- `efswrt!DpmStreamOpenToProtectToIdentity` at `0x1800ba34a`

## pseudocode

```c
__int64 __fastcall DPBuffer::_DoWorkEdp(
        DPBuffer *this,
        int a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned __int64 a5)
{
  _QWORD *v8; // rax
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  _QWORD *v13; // rax
  int v14; // eax
  _QWORD v15[7]; // [rsp+30h] [rbp-38h] BYREF

  v15[0] = 0;
  if ( a2 )
  {
    v8 = tlx::replace<void *,void (*)(void *),&void DpmStreamClose(void *),0>(v15);
    v9 = DpmStreamOpenToProtectToIdentity(a3, 1, DPBuffer::StreamCallback, this, v8);
    if ( v9 < 0 )
    {
      v11 = 168;
      goto LABEL_4;
    }
  }
  else
  {
    v13 = tlx::replace<void *,void (*)(void *),&void DpmStreamClose(void *),0>(v15);
    v9 = DpmStreamOpenToUnprotect(DPBuffer::StreamCallback, this, v13);
    if ( v9 < 0 )
    {
      v11 = 175;
      goto LABEL_4;
    }
  }
  v14 = DpmStreamUpdate(v15[0], a4, a5, 1);
  v9 = v14;
  if ( v14 < 0 )
  {
    if ( v14 == -2146893780 )
      goto LABEL_5;
    v11 = 178;
LABEL_4:
    Log_UnistoreHREvent_3((unsigned int)v9, 1, v10, v11);
LABEL_5:
    if ( v15[0] )
      DpmStreamClose();
    return (unsigned int)v9;
  }
  if ( v15[0] )
    DpmStreamClose();
  return 0;
}

```

## disassembly

```asm
0x1800ba308  push    rbx
0x1800ba30a  push    rbp
0x1800ba30b  push    rsi
0x1800ba30c  push    rdi
0x1800ba30d  sub     rsp, 48h
0x1800ba311  mov     [rsp+68h+var_38], 0
0x1800ba31a  mov     rbx, rcx
0x1800ba31d  lea     rcx, [rsp+68h+var_38]
0x1800ba322  mov     rdi, r9
0x1800ba325  mov     rsi, r8
0x1800ba328  mov     ebp, 1
0x1800ba32d  test    edx, edx
0x1800ba32f  jz      short loc_1800BA379
0x1800ba331  call    ??$replace@PEAXP6AXPEAX@Z$1?DpmStreamClose@@YAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?DpmStreamClose@@YAX0@Z$0A@@0@@Z; tlx::replace<void *,void (*)(void *),&DpmStreamClose(void *),0>(tlx::auto_xxx<void *,void (*)(void *),&DpmStreamClose(void *),0> &)
0x1800ba336  mov     r9, rbx
0x1800ba339  mov     [rsp+68h+var_48], rax
0x1800ba33e  lea     r8, ?StreamCallback@DPBuffer@@SAJPEAXPEBE_KH@Z; DPBuffer::StreamCallback(void *,uchar const *,unsigned __int64,int)
0x1800ba345  mov     edx, ebp
0x1800ba347  mov     rcx, rsi
0x1800ba34a  call    cs:__imp_DpmStreamOpenToProtectToIdentity
0x1800ba350  mov     ebx, eax
0x1800ba352  test    eax, eax
0x1800ba354  jns     short loc_1800BA39F
0x1800ba356  mov     r9d, 0A8h
0x1800ba35c  mov     edx, ebp
0x1800ba35e  mov     ecx, ebx
0x1800ba360  call    Log_UnistoreHREvent_3
0x1800ba365  mov     rcx, [rsp+68h+var_38]
0x1800ba36a  test    rcx, rcx
0x1800ba36d  jz      short loc_1800BA375
0x1800ba36f  call    cs:__imp_DpmStreamClose
0x1800ba375  mov     eax, ebx
0x1800ba377  jmp     short loc_1800BA3DF
0x1800ba379  call    ??$replace@PEAXP6AXPEAX@Z$1?DpmStreamClose@@YAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?DpmStreamClose@@YAX0@Z$0A@@0@@Z; tlx::replace<void *,void (*)(void *),&DpmStreamClose(void *),0>(tlx::auto_xxx<void *,void (*)(void *),&DpmStreamClose(void *),0> &)
0x1800ba37e  mov     r8, rax
0x1800ba381  lea     rcx, ?StreamCallback@DPBuffer@@SAJPEAXPEBE_KH@Z; DPBuffer::StreamCallback(void *,uchar const *,unsigned __int64,int)
0x1800ba388  mov     rdx, rbx
0x1800ba38b  call    cs:__imp_DpmStreamOpenToUnprotect
0x1800ba391  mov     ebx, eax
0x1800ba393  test    eax, eax
0x1800ba395  jns     short loc_1800BA39F
0x1800ba397  mov     r9d, 0AFh
0x1800ba39d  jmp     short loc_1800BA35C
0x1800ba39f  mov     r8, [rsp+68h+arg_20]
0x1800ba3a7  mov     r9d, ebp
0x1800ba3aa  mov     rcx, [rsp+68h+var_38]
0x1800ba3af  mov     rdx, rdi
0x1800ba3b2  call    cs:__imp_DpmStreamUpdate
0x1800ba3b8  mov     ebx, eax
0x1800ba3ba  test    eax, eax
0x1800ba3bc  jns     short loc_1800BA3CD
0x1800ba3be  cmp     eax, 8009002Ch
0x1800ba3c3  jz      short loc_1800BA365
0x1800ba3c5  mov     r9d, 0B2h
0x1800ba3cb  jmp     short loc_1800BA35C
0x1800ba3cd  mov     rcx, [rsp+68h+var_38]
0x1800ba3d2  test    rcx, rcx
0x1800ba3d5  jz      short loc_1800BA3DD
0x1800ba3d7  call    cs:__imp_DpmStreamClose
0x1800ba3dd  xor     eax, eax
0x1800ba3df  add     rsp, 48h
0x1800ba3e3  pop     rdi
0x1800ba3e4  pop     rsi
0x1800ba3e5  pop     rbp
0x1800ba3e6  pop     rbx
0x1800ba3e7  retn
```
