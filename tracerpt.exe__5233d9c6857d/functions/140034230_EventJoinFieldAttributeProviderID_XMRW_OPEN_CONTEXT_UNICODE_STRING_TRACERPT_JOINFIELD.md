# EventJoinFieldAttributeProviderID(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_JOINFIELD *)

- ea: `0x140034230`
- end: `0x140034310`
- name: `?EventJoinFieldAttributeProviderID@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_JOINFIELD@@@Z`
- size: `224`
- prototype: `unsigned int(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_JOINFIELD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14003451c`

## callees

- `0x140034230`
- `0x14003694c`
- `0x140037954`
- `0x140040130`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventJoinFieldAttributeProviderID(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_JOINFIELD *a3)
{
  bool v3; // zf
  __int64 v4; // rsi
  __int64 result; // rax
  unsigned int v8; // edi
  struct _GUID v9; // xmm0
  unsigned int v10; // [rsp+20h] [rbp-38h] BYREF
  struct _GUID v11; // [rsp+28h] [rbp-30h] BYREF

  v3 = (*((_BYTE *)a3 + 176) & 1) == 0;
  v4 = *((_QWORD *)a1 + 3);
  v11 = 0;
  v10 = 0;
  if ( !v3 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x452u, v10);
    return 3221745153LL;
  }
  v8 = StringToGuid(a2, &v11);
  if ( v8 == -1073222112 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x453u, v10, a2);
    return v8;
  }
  if ( v8 )
    return v8;
  v9 = v11;
  *((_BYTE *)a3 + 176) |= 1u;
  result = 0;
  *(struct _GUID *)((char *)a3 + 40) = v9;
  return result;
}

```

## disassembly

```asm
0x140034230  mov     [rsp+arg_18], rbx
0x140034235  push    rbp
0x140034236  push    rsi
0x140034237  push    rdi
0x140034238  sub     rsp, 40h
0x14003423c  mov     rax, cs:__security_cookie
0x140034243  xor     rax, rsp
0x140034246  mov     [rsp+58h+var_20], rax
0x14003424b  test    byte ptr [r8+0B0h], 1
0x140034253  xorps   xmm0, xmm0
0x140034256  mov     rsi, [rcx+18h]
0x14003425a  mov     rbx, r8
0x14003425d  movups  xmmword ptr [rsp+58h+var_30.Data1], xmm0
0x140034262  mov     rbp, rdx
0x140034265  mov     [rsp+58h+var_38], 0
0x14003426d  jz      short loc_14003429B
0x14003426f  mov     rax, [rsi]
0x140034272  lea     rdx, [rsp+58h+var_38]
0x140034277  mov     rcx, rsi
0x14003427a  mov     rax, [rax+0A8h]
0x140034281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034286  mov     edx, [rsp+58h+var_38]
0x14003428a  mov     ecx, 452h; unsigned int
0x14003428f  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034294  mov     eax, 0C007EE01h
0x140034299  jmp     short loc_1400342F6
0x14003429b  lea     rdx, [rsp+58h+var_30]; struct _GUID *
0x1400342a0  mov     rcx, rbp; struct _UNICODE_STRING *
0x1400342a3  call    ?StringToGuid@@YAKAEAU_UNICODE_STRING@@PEAU_GUID@@@Z; StringToGuid(_UNICODE_STRING &,_GUID *)
0x1400342a8  mov     edi, eax
0x1400342aa  cmp     eax, 0C007EE20h
0x1400342af  jnz     short loc_1400342DB
0x1400342b1  mov     rcx, [rsi]
0x1400342b4  lea     rdx, [rsp+58h+var_38]
0x1400342b9  mov     rax, [rcx+0A8h]
0x1400342c0  mov     rcx, rsi
0x1400342c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400342c8  mov     edx, [rsp+58h+var_38]
0x1400342cc  mov     r8, rbp
0x1400342cf  mov     ecx, 453h; unsigned int
0x1400342d4  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400342d9  jmp     short loc_1400342DF
0x1400342db  test    edi, edi
0x1400342dd  jz      short loc_1400342E3
0x1400342df  mov     eax, edi
0x1400342e1  jmp     short loc_1400342F6
0x1400342e3  movups  xmm0, xmmword ptr [rsp+58h+var_30.Data1]
0x1400342e8  or      byte ptr [rbx+0B0h], 1
0x1400342ef  xor     eax, eax
0x1400342f1  movdqu  xmmword ptr [rbx+28h], xmm0
0x1400342f6  mov     rcx, [rsp+58h+var_20]
0x1400342fb  xor     rcx, rsp; StackCookie
0x1400342fe  call    __security_check_cookie
0x140034303  mov     rbx, [rsp+58h+arg_18]
0x140034308  add     rsp, 40h
0x14003430c  pop     rdi
0x14003430d  pop     rsi
0x14003430e  pop     rbp
0x14003430f  retn
```
