# CreateStreamInputSource(IMalloc *,IUnknown *,bool,InputSource * *)

- ea: `0x1004171c0`
- end: `0x1004172d4`
- name: `?CreateStreamInputSource@@YAJPEAUIMalloc@@PEAUIUnknown@@_NPEAPEAVInputSource@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(struct IMalloc *, struct IUnknown *, bool, struct InputSource **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x100402f30`
- `0x10040a750`

## callees

- `0x10040cc10`
- `0x1004171c0`
- `0x1004172e0`
- `0x100417490`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall CreateStreamInputSource(struct IMalloc *a1, struct IUnknown *a2, char a3, struct InputSource **a4)
{
  unsigned int v7; // ebx
  StreamInputSource *v8; // rax
  SeekableStreamInputSource *v9; // rax
  struct ISequentialStream *v11[5]; // [rsp+30h] [rbp-28h] BYREF

  v7 = 0;
  v11[0] = 0;
  *a4 = 0;
  if ( !a3
    && ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct ISequentialStream **))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_ISequentialStream,
         v11) >= 0
    && v11[0] )
  {
    v8 = (StreamInputSource *)Base::operator new(0x40u, a1);
    if ( v8 )
    {
      *a4 = StreamInputSource::StreamInputSource(v8, a1, v11[0]);
      goto LABEL_12;
    }
LABEL_10:
    *a4 = 0;
    goto LABEL_12;
  }
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct ISequentialStream **))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IStream,
         v11) >= 0
    && v11[0] )
  {
    v9 = (SeekableStreamInputSource *)Base::operator new(0x40u, a1);
    if ( v9 )
    {
      *a4 = SeekableStreamInputSource::SeekableStreamInputSource(v9, a1, (struct IStream *)v11[0]);
      goto LABEL_12;
    }
    goto LABEL_10;
  }
  v7 = -2147024809;
LABEL_12:
  if ( v11[0] )
    ((void (__fastcall *)(struct ISequentialStream *))v11[0]->lpVtbl->Release)(v11[0]);
  return v7;
}

```

## disassembly

```asm
0x1004171c0  mov     [rsp+arg_0], rbx
0x1004171c5  mov     [rsp+arg_8], rsi
0x1004171ca  mov     [rsp+arg_10], rdi
0x1004171cf  push    r14
0x1004171d1  sub     rsp, 50h
0x1004171d5  mov     rdi, r9
0x1004171d8  mov     r14, rdx
0x1004171db  mov     rsi, rcx
0x1004171de  xor     ebx, ebx
0x1004171e0  mov     [rsp+58h+var_30], ebx
0x1004171e4  mov     [rsp+58h+var_28], rbx
0x1004171e9  mov     [r9], rbx
0x1004171ec  test    r8b, r8b
0x1004171ef  jnz     short loc_10041723C
0x1004171f1  mov     rax, [rdx]
0x1004171f4  lea     r8, [rsp+58h+var_28]
0x1004171f9  lea     rdx, IID_ISequentialStream
0x100417200  mov     rcx, r14
0x100417203  mov     rax, [rax]
0x100417206  call    cs:__guard_dispatch_icall_fptr
0x10041720c  test    eax, eax
0x10041720e  js      short loc_10041723C
0x100417210  cmp     [rsp+58h+var_28], rbx
0x100417215  jz      short loc_10041723C
0x100417217  mov     rdx, rsi; struct IMalloc *
0x10041721a  lea     ecx, [rbx+40h]; dwBytes
0x10041721d  call    ??2Base@@SAPEAX_KPEAUIMalloc@@@Z; Base::operator new(unsigned __int64,IMalloc *)
0x100417222  test    rax, rax
0x100417225  jz      short loc_10041728A
0x100417227  mov     r8, [rsp+58h+var_28]; struct ISequentialStream *
0x10041722c  mov     rdx, rsi; struct IMalloc *
0x10041722f  mov     rcx, rax; this
0x100417232  call    ??0StreamInputSource@@QEAA@PEAUIMalloc@@PEAUISequentialStream@@@Z; StreamInputSource::StreamInputSource(IMalloc *,ISequentialStream *)
0x100417237  mov     [rdi], rax
0x10041723a  jmp     short loc_10041729B
0x10041723c  mov     rax, [r14]
0x10041723f  lea     r8, [rsp+58h+var_28]
0x100417244  lea     rdx, IID_IStream
0x10041724b  mov     rcx, r14
0x10041724e  mov     rax, [rax]
0x100417251  call    cs:__guard_dispatch_icall_fptr
0x100417257  test    eax, eax
0x100417259  js      short loc_100417292
0x10041725b  cmp     [rsp+58h+var_28], 0
0x100417261  jz      short loc_100417292
0x100417263  mov     rdx, rsi; struct IMalloc *
0x100417266  mov     ecx, 40h ; '@'; dwBytes
0x10041726b  call    ??2Base@@SAPEAX_KPEAUIMalloc@@@Z; Base::operator new(unsigned __int64,IMalloc *)
0x100417270  test    rax, rax
0x100417273  jz      short loc_10041728A
0x100417275  mov     r8, [rsp+58h+var_28]; struct IStream *
0x10041727a  mov     rdx, rsi; struct IMalloc *
0x10041727d  mov     rcx, rax; this
0x100417280  call    ??0SeekableStreamInputSource@@QEAA@PEAUIMalloc@@PEAUIStream@@@Z; SeekableStreamInputSource::SeekableStreamInputSource(IMalloc *,IStream *)
0x100417285  mov     [rdi], rax
0x100417288  jmp     short loc_10041729B
0x10041728a  mov     rax, rbx
0x10041728d  mov     [rdi], rbx
0x100417290  jmp     short loc_10041729B
0x100417292  mov     ebx, 80070057h
0x100417297  mov     [rsp+58h+var_30], ebx
0x10041729b  jmp     short loc_1004172A5
0x10041729d  mov     ebx, [rsp+58h+var_38]
0x1004172a1  mov     [rsp+58h+var_30], ebx
0x1004172a5  mov     rcx, [rsp+58h+var_28]
0x1004172aa  test    rcx, rcx
0x1004172ad  jz      short loc_1004172BC
0x1004172af  mov     rdx, [rcx]
0x1004172b2  mov     rax, [rdx+10h]
0x1004172b6  call    cs:__guard_dispatch_icall_fptr
0x1004172bc  mov     eax, ebx
0x1004172be  mov     rbx, [rsp+58h+arg_0]
0x1004172c3  mov     rsi, [rsp+58h+arg_8]
0x1004172c8  mov     rdi, [rsp+58h+arg_10]
0x1004172cd  add     rsp, 50h
0x1004172d1  pop     r14
0x1004172d3  retn
0x10043a1c0  push    rbp
0x10043a1c2  sub     rsp, 20h
0x10043a1c6  mov     rbp, rdx
0x10043a1c9  mov     [rbp+48h], rcx
0x10043a1cd  mov     [rbp+40h], rcx
0x10043a1d1  mov     rax, [rbp+40h]
0x10043a1d5  mov     rcx, [rax]
0x10043a1d8  mov     [rbp+38h], rcx
0x10043a1dc  mov     rax, [rbp+38h]
0x10043a1e0  mov     eax, [rax]
0x10043a1e2  cmp     eax, 0C0000005h
0x10043a1e7  jz      short loc_10043A219
0x10043a1e9  add     eax, 1FFFFFFFh
0x10043a1ee  cmp     eax, 1
0x10043a1f1  ja      short loc_10043A209
0x10043a1f3  mov     rax, [rbp+38h]
0x10043a1f7  cmp     dword ptr [rax+18h], 1
0x10043a1fb  jnz     short loc_10043A209
0x10043a1fd  mov     rax, [rbp+38h]
0x10043a201  mov     ecx, [rax+20h]
0x10043a204  mov     [rbp+20h], ecx
0x10043a207  jmp     short loc_10043A210
0x10043a209  mov     dword ptr [rbp+20h], 8000FFFFh
0x10043a210  mov     dword ptr [rbp+24h], 1
0x10043a217  jmp     short loc_10043A220
0x10043a219  mov     dword ptr [rbp+24h], 0
0x10043a220  mov     eax, [rbp+24h]
0x10043a223  add     rsp, 20h
0x10043a227  pop     rbp
0x10043a228  retn
```
