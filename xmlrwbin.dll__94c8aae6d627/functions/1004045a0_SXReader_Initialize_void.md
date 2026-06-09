# SXReader::Initialize(void)

- ea: `0x1004045a0`
- end: `0x1004047a6`
- name: `?Initialize@SXReader@@QEAAXXZ`
- size: `518`
- prototype: `void __fastcall(SXReader *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x100404170`

## callees

- `0x100401350`
- `0x1004045a0`
- `0x100406550`
- `0x100407050`
- `0x100410d20`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1004045ff`
- `KERNEL32!HeapAlloc` at `0x1004046cb`
- `KERNEL32!HeapAlloc` at `0x10040474a`
- `KERNEL32!HeapAlloc` at `0x1004045ff`
- `KERNEL32!HeapAlloc` at `0x1004046cb`
- `KERNEL32!HeapAlloc` at `0x10040474a`

## pseudocode

```c
void __fastcall SXReader::Initialize(SXReader *this)
{
  __int64 v1; // rsi
  _QWORD *v3; // rax
  _QWORD *v4; // rdi
  __int64 v5; // rcx
  struct IMalloc *v6; // rcx
  LPVOID v7; // rax
  char *v8; // rdi
  __int64 i; // rsi
  struct IMalloc *v10; // rcx
  LPVOID v11; // rax
  struct IMalloc *v12; // rcx

  v1 = *((_QWORD *)this + 1);
  if ( v1 )
  {
    v3 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v1 + 24LL))(*((_QWORD *)this + 1), 104);
  }
  else if ( g_pMalloc )
  {
    v3 = (_QWORD *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 104);
  }
  else
  {
    v3 = HeapAlloc(g_hHeap, 0, 0x68u);
  }
  v4 = v3;
  if ( !v3 )
    goto LABEL_22;
  v3[1] = v1;
  v5 = *((_QWORD *)this + 1);
  v3[1] = v5;
  *v3 = &SXAttributes::`vftable'{for `Base'};
  v3[2] = &SXAttributes::`vftable'{for `ISXFormatAttributes'};
  v3[4] = &_xarray<AttributeData,_xarray_item_new_<AttributeData>>::`vftable';
  v3[8] = &_xarray<AttributeNS,_xarray_item_new_<AttributeNS>>::`vftable';
  *((_DWORD *)v3 + 6) = 1;
  v3[5] = v5;
  v3[6] = 0;
  v3[7] = 0;
  v3[9] = v5;
  v3[10] = 0;
  v3[11] = 0;
  v3[12] = this;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  v6 = (struct IMalloc *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 188) = v4;
  *((_DWORD *)this + 378) = 32;
  if ( v6 || (v6 = g_pMalloc) != 0 )
    v7 = (LPVOID)((__int64 (__fastcall *)(struct IMalloc *, __int64))v6->lpVtbl->Alloc)(v6, 32);
  else
    v7 = HeapAlloc(g_hHeap, 0, 0x20u);
  if ( !v7 )
  {
LABEL_22:
    MXRRaiseException(-2147024882);
    JUMPOUT(0x1004047A5LL);
  }
  *((_QWORD *)this + 190) = v7;
  *((_BYTE *)this + 1528) = 0;
  *((_DWORD *)this + 280) = 0;
  dword_100434BC0 = 0;
  RStringPtr::assign((RStringPtr *)&rspNull, (struct CStringPtr *)&cspNull);
  *((_DWORD *)this + 174) = 0;
  v8 = (char *)this + 16;
  for ( i = 0; i < 4; ++i )
  {
    v10 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v10 || (v10 = g_pMalloc) != 0 )
      v11 = (LPVOID)((__int64 (__fastcall *)(struct IMalloc *, __int64))v10->lpVtbl->Alloc)(v10, 64);
    else
      v11 = HeapAlloc(g_hHeap, 0, 0x40u);
    if ( !v11 )
      goto LABEL_22;
    *((_QWORD *)v8 + 1) = v11;
    *(_DWORD *)v8 = 32;
    v8 += 16;
  }
  v12 = (struct IMalloc *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 90) = 0;
  SXTokenTable::PushTokenTable(v12, (struct SXTokenTable **)this + 90);
  SXReadBase::XmlNsReset(this);
}

```

## disassembly

```asm
0x1004045a0  mov     [rsp+arg_8], rbx
0x1004045a5  mov     [rsp+arg_10], rsi
0x1004045aa  push    rdi
0x1004045ab  sub     rsp, 20h
0x1004045af  mov     rsi, [rcx+8]
0x1004045b3  mov     rbx, rcx
0x1004045b6  test    rsi, rsi
0x1004045b9  jz      short loc_1004045D2
0x1004045bb  mov     rax, [rsi]
0x1004045be  mov     edx, 68h ; 'h'
0x1004045c3  mov     rcx, rsi
0x1004045c6  mov     rax, [rax+18h]
0x1004045ca  call    cs:__guard_dispatch_icall_fptr
0x1004045d0  jmp     short loc_100404605
0x1004045d2  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004045d9  test    rcx, rcx
0x1004045dc  jz      short loc_1004045F2
0x1004045de  mov     rax, [rcx]
0x1004045e1  mov     edx, 68h ; 'h'
0x1004045e6  mov     rax, [rax+18h]
0x1004045ea  call    cs:__guard_dispatch_icall_fptr
0x1004045f0  jmp     short loc_100404605
0x1004045f2  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004045f9  xor     edx, edx; dwFlags
0x1004045fb  lea     r8d, [rdx+68h]; dwBytes
0x1004045ff  call    cs:__imp_HeapAlloc
0x100404605  mov     [rsp+28h+arg_0], rbp
0x10040460a  mov     rdi, rax
0x10040460d  test    rax, rax
0x100404610  jz      loc_10040479B
0x100404616  mov     [rax+8], rsi
0x10040461a  xor     ebp, ebp
0x10040461c  mov     rcx, [rbx+8]
0x100404620  mov     [rax+8], rcx
0x100404624  lea     rax, ??_7SXAttributes@@6BBase@@@; const SXAttributes::`vftable'{for `Base'}
0x10040462b  mov     [rdi], rax
0x10040462e  lea     rax, ??_7SXAttributes@@6BISXFormatAttributes@@@; const SXAttributes::`vftable'{for `ISXFormatAttributes'}
0x100404635  mov     [rdi+10h], rax
0x100404639  lea     rax, ??_7?$_xarray@VAttributeData@@V?$_xarray_item_new_@VAttributeData@@@@@@6B@; const _xarray<AttributeData,_xarray_item_new_<AttributeData>>::`vftable'
0x100404640  mov     [rdi+20h], rax
0x100404644  lea     rax, ??_7?$_xarray@VAttributeNS@@V?$_xarray_item_new_@VAttributeNS@@@@@@6B@; const _xarray<AttributeNS,_xarray_item_new_<AttributeNS>>::`vftable'
0x10040464b  mov     [rdi+40h], rax
0x10040464f  mov     dword ptr [rdi+18h], 1
0x100404656  mov     [rdi+28h], rcx
0x10040465a  mov     [rdi+30h], rbp
0x10040465e  mov     [rdi+38h], rbp
0x100404662  mov     [rdi+48h], rcx
0x100404666  mov     [rdi+50h], rbp
0x10040466a  mov     [rdi+58h], rbp
0x10040466e  mov     [rdi+60h], rbx
0x100404672  test    rcx, rcx
0x100404675  jz      short loc_100404684
0x100404677  mov     rax, [rcx]
0x10040467a  mov     rax, [rax+8]
0x10040467e  call    cs:__guard_dispatch_icall_fptr
0x100404684  mov     rcx, [rbx+8]
0x100404688  mov     [rbx+5E0h], rdi
0x10040468f  mov     dword ptr [rbx+5E8h], 20h ; ' '
0x100404699  test    rcx, rcx
0x10040469c  jnz     short loc_1004046AA
0x10040469e  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004046a5  test    rcx, rcx
0x1004046a8  jz      short loc_1004046BE
0x1004046aa  mov     rax, [rcx]
0x1004046ad  mov     edx, 20h ; ' '
0x1004046b2  mov     rax, [rax+18h]
0x1004046b6  call    cs:__guard_dispatch_icall_fptr
0x1004046bc  jmp     short loc_1004046D1
0x1004046be  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004046c5  xor     edx, edx; dwFlags
0x1004046c7  lea     r8d, [rdx+20h]; dwBytes
0x1004046cb  call    cs:__imp_HeapAlloc
0x1004046d1  test    rax, rax
0x1004046d4  jz      loc_10040479B
0x1004046da  mov     [rbx+5F0h], rax
0x1004046e1  lea     rdx, ?cspNull@@3VCStringPtr@@A; struct CStringPtr *
0x1004046e8  mov     [rbx+5F8h], bpl
0x1004046ef  lea     rcx, ?rspNull@@3VRStringPtr@@A; this
0x1004046f6  mov     [rbx+460h], ebp
0x1004046fc  mov     cs:dword_100434BC0, ebp
0x100404702  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100404707  mov     [rbx+2B8h], ebp
0x10040470d  lea     rdi, [rbx+10h]
0x100404711  mov     rsi, rbp
0x100404714  mov     rcx, [rbx+8]
0x100404718  test    rcx, rcx
0x10040471b  jnz     short loc_100404729
0x10040471d  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100404724  test    rcx, rcx
0x100404727  jz      short loc_10040473D
0x100404729  mov     rax, [rcx]
0x10040472c  mov     edx, 40h ; '@'
0x100404731  mov     rax, [rax+18h]
0x100404735  call    cs:__guard_dispatch_icall_fptr
0x10040473b  jmp     short loc_100404750
0x10040473d  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100404744  xor     edx, edx; dwFlags
0x100404746  lea     r8d, [rdx+40h]; dwBytes
0x10040474a  call    cs:__imp_HeapAlloc
0x100404750  test    rax, rax
0x100404753  jz      short loc_10040479B
0x100404755  mov     [rdi+8], rax
0x100404759  inc     rsi
0x10040475c  mov     dword ptr [rdi], 20h ; ' '
0x100404762  add     rdi, 10h
0x100404766  cmp     rsi, 4
0x10040476a  jl      short loc_100404714
0x10040476c  mov     rcx, [rbx+8]; struct IMalloc *
0x100404770  lea     rdx, [rbx+2D0h]; struct SXTokenTable **
0x100404777  mov     [rdx], rbp
0x10040477a  call    ?PushTokenTable@SXTokenTable@@SAXPEAUIMalloc@@PEAPEAV1@@Z; SXTokenTable::PushTokenTable(IMalloc *,SXTokenTable * *)
0x10040477f  mov     rcx, rbx; this
0x100404782  mov     rbp, [rsp+28h+arg_0]
0x100404787  mov     rbx, [rsp+28h+arg_8]
0x10040478c  mov     rsi, [rsp+28h+arg_10]
0x100404791  add     rsp, 20h
0x100404795  pop     rdi
0x100404796  jmp     ?XmlNsReset@SXReadBase@@IEAAXXZ; SXReadBase::XmlNsReset(void)
0x10040479b  mov     ecx, 8007000Eh; int
0x1004047a0  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
