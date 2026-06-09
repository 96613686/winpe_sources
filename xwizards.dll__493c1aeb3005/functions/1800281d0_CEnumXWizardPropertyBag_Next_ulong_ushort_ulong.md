# CEnumXWizardPropertyBag::Next(ulong,ushort * *,ulong *)

- ea: `0x1800281d0`
- end: `0x180028305`
- name: `?Next@CEnumXWizardPropertyBag@@UEAAJKPEAPEAGPEAK@Z`
- size: `309`
- prototype: `int(CEnumXWizardPropertyBag *__hidden this, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008634`
- `0x18000ae04`
- `0x1800281d0`
- `0x180032a02`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002822d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002822d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002827f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002829a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002827f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002829a`

## pseudocode

```c
__int64 __fastcall CEnumXWizardPropertyBag::Next(
        CEnumXWizardPropertyBag *this,
        unsigned int a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  int v8; // edi
  __int64 v9; // rsi
  unsigned __int16 *v10; // rbx
  __int64 i; // rbp

  if ( a3 && (a4 || a2 == 1) )
  {
    v8 = 0;
    v9 = 0;
    if ( a4 )
      *a4 = 0;
    memset_0(a3, 0, 8LL * a2);
    while ( 1 )
    {
      if ( (unsigned int)v9 >= a2 )
        goto LABEL_17;
      v10 = (unsigned __int16 *)CoTaskMemAlloc(0x66u);
      if ( !v10 )
      {
        v8 = -2147024882;
        goto LABEL_14;
      }
      v8 = (*(__int64 (__fastcall **)(_QWORD, char *, char *, char *))(**((_QWORD **)this + 27) + 32LL))(
             *((_QWORD *)this + 27),
             (char *)this + 64,
             (char *)this + 80,
             (char *)this + 96);
      if ( v8 )
        break;
      *v10 = 0;
      StringCchCopyW(v10, 0x33u, (const unsigned __int16 *)this + 56);
      a3[v9] = v10;
      v9 = (unsigned int)(v9 + 1);
    }
    CoTaskMemFree(v10);
    if ( v8 < 0 )
    {
LABEL_14:
      for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
      {
        CoTaskMemFree(a3[i]);
        a3[i] = 0;
      }
      goto LABEL_20;
    }
LABEL_17:
    if ( a4 )
      *a4 = v9;
  }
  else
  {
    v8 = -2147467261;
  }
LABEL_20:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fffc769325f23264b7d628afdee77bf5_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800281d0  push    rbx
0x1800281d2  push    rbp
0x1800281d3  push    rsi
0x1800281d4  push    rdi
0x1800281d5  push    r12
0x1800281d7  push    r13
0x1800281d9  push    r14
0x1800281db  push    r15
0x1800281dd  sub     rsp, 38h
0x1800281e1  mov     ebp, edx
0x1800281e3  mov     r14, r9
0x1800281e6  mov     r15, r8
0x1800281e9  mov     r13, rcx
0x1800281ec  test    r8, r8
0x1800281ef  jz      loc_1800282BC
0x1800281f5  test    r9, r9
0x1800281f8  jnz     short loc_180028203
0x1800281fa  cmp     ebp, 1
0x1800281fd  jnz     loc_1800282BC
0x180028203  xor     edi, edi
0x180028205  xor     esi, esi
0x180028207  test    r14, r14
0x18002820a  jz      short loc_18002820F
0x18002820c  mov     [r9], esi
0x18002820f  mov     r8, rbp
0x180028212  xor     edx, edx; Val
0x180028214  shl     r8, 3; Size
0x180028218  mov     rcx, r15; void *
0x18002821b  call    memset_0
0x180028220  cmp     esi, ebp
0x180028222  jnb     loc_1800282B2
0x180028228  mov     ecx, 66h ; 'f'; cb
0x18002822d  call    cs:__imp_CoTaskMemAlloc
0x180028233  mov     rbx, rax
0x180028236  test    rax, rax
0x180028239  jz      short loc_18002828B
0x18002823b  mov     rcx, [r13+0D8h]
0x180028242  lea     r8, [r13+50h]
0x180028246  lea     rdx, [r13+40h]
0x18002824a  lea     r9, [r13+60h]
0x18002824e  mov     rax, [rcx]
0x180028251  mov     rax, [rax+20h]
0x180028255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002825a  mov     edi, eax
0x18002825c  test    eax, eax
0x18002825e  jnz     short loc_18002827C
0x180028260  xor     ecx, ecx
0x180028262  lea     r8, [r13+70h]; unsigned __int16 *
0x180028266  mov     [rbx], cx
0x180028269  lea     edx, [rax+33h]; unsigned __int64
0x18002826c  mov     rcx, rbx; unsigned __int16 *
0x18002826f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028274  mov     [r15+rsi*8], rbx
0x180028278  inc     esi
0x18002827a  jmp     short loc_180028220
0x18002827c  mov     rcx, rbx; pv
0x18002827f  call    cs:__imp_CoTaskMemFree
0x180028285  test    edi, edi
0x180028287  jns     short loc_1800282B2
0x180028289  jmp     short loc_180028290
0x18002828b  mov     edi, 8007000Eh
0x180028290  xor     ebp, ebp
0x180028292  test    esi, esi
0x180028294  jz      short loc_1800282C1
0x180028296  mov     rcx, [r15+rbp*8]; pv
0x18002829a  call    cs:__imp_CoTaskMemFree
0x1800282a0  mov     qword ptr [r15+rbp*8], 0
0x1800282a8  inc     ebp
0x1800282aa  cmp     ebp, esi
0x1800282ac  jb      short loc_180028296
0x1800282ae  test    edi, edi
0x1800282b0  js      short loc_1800282C1
0x1800282b2  test    r14, r14
0x1800282b5  jz      short loc_1800282C1
0x1800282b7  mov     [r14], esi
0x1800282ba  jmp     short loc_1800282C1
0x1800282bc  mov     edi, 80004003h
0x1800282c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282c8  lea     rax, WPP_GLOBAL_Control
0x1800282cf  cmp     rcx, rax
0x1800282d2  jz      short loc_1800282F2
0x1800282d4  test    byte ptr [rcx+1Ch], 10h
0x1800282d8  jz      short loc_1800282F2
0x1800282da  mov     rcx, [rcx+10h]
0x1800282de  lea     r8, WPP_fffc769325f23264b7d628afdee77bf5_Traceguids
0x1800282e5  mov     edx, 0Ah
0x1800282ea  mov     r9d, edi
0x1800282ed  call    WPP_SF_d
0x1800282f2  mov     eax, edi
0x1800282f4  add     rsp, 38h
0x1800282f8  pop     r15
0x1800282fa  pop     r14
0x1800282fc  pop     r13
0x1800282fe  pop     r12
0x180028300  pop     rdi
0x180028301  pop     rsi
0x180028302  pop     rbp
0x180028303  pop     rbx
0x180028304  retn
```
