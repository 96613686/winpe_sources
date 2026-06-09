# EventFieldAttributeProviderID(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_FIELD *)

- ea: `0x140033810`
- end: `0x1400338f0`
- name: `?EventFieldAttributeProviderID@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_FIELD@@@Z`
- size: `224`
- prototype: `unsigned int(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_FIELD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400339c8`

## callees

- `0x140033810`
- `0x14003694c`
- `0x140037954`
- `0x140040130`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventFieldAttributeProviderID(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_FIELD *a3)
{
  bool v3; // zf
  __int64 v4; // rsi
  __int64 result; // rax
  unsigned int v8; // edi
  struct _GUID v9; // xmm0
  unsigned int v10; // [rsp+20h] [rbp-38h] BYREF
  struct _GUID v11; // [rsp+28h] [rbp-30h] BYREF

  v3 = (*((_BYTE *)a3 + 216) & 4) == 0;
  v4 = *((_QWORD *)a1 + 3);
  v11 = 0;
  v10 = 0;
  if ( !v3 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x443u, v10);
    return 3221745153LL;
  }
  v8 = StringToGuid(a2, &v11);
  if ( v8 == -1073222112 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x445u, v10, a2);
    return v8;
  }
  if ( v8 )
    return v8;
  v9 = v11;
  *((_BYTE *)a3 + 216) |= 4u;
  result = 0;
  *((struct _GUID *)a3 + 5) = v9;
  return result;
}

```

## disassembly

```asm
0x140033810  mov     [rsp+arg_18], rbx
0x140033815  push    rbp
0x140033816  push    rsi
0x140033817  push    rdi
0x140033818  sub     rsp, 40h
0x14003381c  mov     rax, cs:__security_cookie
0x140033823  xor     rax, rsp
0x140033826  mov     [rsp+58h+var_20], rax
0x14003382b  test    byte ptr [r8+0D8h], 4
0x140033833  xorps   xmm0, xmm0
0x140033836  mov     rsi, [rcx+18h]
0x14003383a  mov     rbx, r8
0x14003383d  movups  xmmword ptr [rsp+58h+var_30.Data1], xmm0
0x140033842  mov     rbp, rdx
0x140033845  mov     [rsp+58h+var_38], 0
0x14003384d  jz      short loc_14003387B
0x14003384f  mov     rax, [rsi]
0x140033852  lea     rdx, [rsp+58h+var_38]
0x140033857  mov     rcx, rsi
0x14003385a  mov     rax, [rax+0A8h]
0x140033861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033866  mov     edx, [rsp+58h+var_38]
0x14003386a  mov     ecx, 443h; unsigned int
0x14003386f  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140033874  mov     eax, 0C007EE01h
0x140033879  jmp     short loc_1400338D6
0x14003387b  lea     rdx, [rsp+58h+var_30]; struct _GUID *
0x140033880  mov     rcx, rbp; struct _UNICODE_STRING *
0x140033883  call    ?StringToGuid@@YAKAEAU_UNICODE_STRING@@PEAU_GUID@@@Z; StringToGuid(_UNICODE_STRING &,_GUID *)
0x140033888  mov     edi, eax
0x14003388a  cmp     eax, 0C007EE20h
0x14003388f  jnz     short loc_1400338BB
0x140033891  mov     rcx, [rsi]
0x140033894  lea     rdx, [rsp+58h+var_38]
0x140033899  mov     rax, [rcx+0A8h]
0x1400338a0  mov     rcx, rsi
0x1400338a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400338a8  mov     edx, [rsp+58h+var_38]
0x1400338ac  mov     r8, rbp
0x1400338af  mov     ecx, 445h; unsigned int
0x1400338b4  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400338b9  jmp     short loc_1400338BF
0x1400338bb  test    edi, edi
0x1400338bd  jz      short loc_1400338C3
0x1400338bf  mov     eax, edi
0x1400338c1  jmp     short loc_1400338D6
0x1400338c3  movups  xmm0, xmmword ptr [rsp+58h+var_30.Data1]
0x1400338c8  or      byte ptr [rbx+0D8h], 4
0x1400338cf  xor     eax, eax
0x1400338d1  movdqu  xmmword ptr [rbx+50h], xmm0
0x1400338d6  mov     rcx, [rsp+58h+var_20]
0x1400338db  xor     rcx, rsp; StackCookie
0x1400338de  call    __security_check_cookie
0x1400338e3  mov     rbx, [rsp+58h+arg_18]
0x1400338e8  add     rsp, 40h
0x1400338ec  pop     rdi
0x1400338ed  pop     rsi
0x1400338ee  pop     rbp
0x1400338ef  retn
```
