# CSWbemProxyCache::CSWbemProxyCache(IUnknown *,_COAUTHIDENTITY *,ushort *,ushort *)

- ea: `0x18001cc78`
- end: `0x18001cd7e`
- name: `??0CSWbemProxyCache@@QEAA@PEAUIUnknown@@PEAU_COAUTHIDENTITY@@PEAG2@Z`
- size: `262`
- prototype: `CSWbemProxyCache *__usercall@<rax>(CSWbemProxyCache *__hidden this@<rcx>, struct IUnknown *@<rdx>, struct _COAUTHIDENTITY *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001e5dc`
- `0x18001e8bc`

## callees

- `0x18000a7b0`
- `0x1800112d0`
- `0x18001cc78`
- `0x180033b34`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001ccef`
- `OLEAUT32!__imp_SysAllocString` at `0x18001cd04`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ccef`
- `OLEAUT32!__imp_SysAllocString` at `0x18001cd04`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CSWbemProxyCache *__fastcall CSWbemProxyCache::CSWbemProxyCache(
        CSWbemProxyCache *this,
        struct IUnknown *a2,
        struct _COAUTHIDENTITY *a3,
        unsigned __int16 *a4,
        unsigned __int16 *psz)
{
  __int64 **v9; // rsi
  __int64 *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  bool v13; // zf
  char v14; // al

  *(_QWORD *)this = &CSWbemProxyCache::`vftable';
  CCritSec::CCritSec((CSWbemProxyCache *)((char *)this + 16));
  *((_DWORD *)this + 2) = 1;
  v9 = (__int64 **)((char *)this + 280);
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_WORD *)this + 160) = 1;
  if ( psz )
    *((_QWORD *)this + 37) = SysAllocString(psz);
  if ( a4 )
    *((_QWORD *)this + 36) = SysAllocString(a4);
  if ( a3 )
    WbemAllocAuthIdentity(a3->User, a3->Password, a3->Domain, (struct _COAUTHIDENTITY **)this + 35);
  v10 = *v9;
  if ( !*v9 )
    goto LABEL_12;
  v11 = *v10;
  if ( !*v10 )
    goto LABEL_12;
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(v11 + 2 * v12) );
  v13 = v12 == 0;
  v14 = 1;
  if ( v13 )
LABEL_12:
    v14 = 0;
  *((_BYTE *)this + 321) = v14;
  CSWbemProxyCache::InitializeCache(this, a2, 0, 1, 1);
  return this;
}

```

## disassembly

```asm
0x18001cc78  mov     [rsp+arg_0], rcx
0x18001cc7d  push    rbx
0x18001cc7e  push    rbp
0x18001cc7f  push    rsi
0x18001cc80  push    rdi
0x18001cc81  push    r14
0x18001cc83  push    r15
0x18001cc85  sub     rsp, 38h
0x18001cc89  mov     rbp, r9
0x18001cc8c  mov     rdi, r8
0x18001cc8f  mov     r14, rdx
0x18001cc92  mov     rbx, rcx
0x18001cc95  lea     rax, ??_7CSWbemProxyCache@@6B@; const CSWbemProxyCache::`vftable'
0x18001cc9c  mov     [rcx], rax
0x18001cc9f  add     rcx, 10h; this
0x18001cca3  call    ??0CCritSec@@QEAA@XZ; CCritSec::CCritSec(void)
0x18001cca8  nop
0x18001cca9  mov     dword ptr [rbx+8], 1
0x18001ccb0  lea     rsi, [rbx+118h]
0x18001ccb7  xor     r15d, r15d
0x18001ccba  mov     [rsi], r15
0x18001ccbd  mov     [rbx+120h], r15
0x18001ccc4  mov     [rbx+128h], r15
0x18001cccb  mov     [rbx+130h], r15
0x18001ccd2  mov     [rbx+138h], r15
0x18001ccd9  mov     word ptr [rbx+140h], 1
0x18001cce2  mov     rcx, [rsp+68h+psz]; psz
0x18001ccea  test    rcx, rcx
0x18001cced  jz      short loc_18001CCFC
0x18001ccef  call    cs:__imp_SysAllocString
0x18001ccf5  mov     [rbx+128h], rax
0x18001ccfc  test    rbp, rbp
0x18001ccff  jz      short loc_18001CD11
0x18001cd01  mov     rcx, rbp; psz
0x18001cd04  call    cs:__imp_SysAllocString
0x18001cd0a  mov     [rbx+120h], rax
0x18001cd11  test    rdi, rdi
0x18001cd14  jz      short loc_18001CD29
0x18001cd16  mov     r9, rsi; struct _COAUTHIDENTITY **
0x18001cd19  mov     r8, [rdi+10h]; unsigned __int16 *
0x18001cd1d  mov     rdx, [rdi+20h]; unsigned __int16 *
0x18001cd21  mov     rcx, [rdi]; unsigned __int16 *
0x18001cd24  call    ?WbemAllocAuthIdentity@@YAJPEBG00PEAPEAU_COAUTHIDENTITY@@@Z; WbemAllocAuthIdentity(ushort const *,ushort const *,ushort const *,_COAUTHIDENTITY * *)
0x18001cd29  mov     rax, [rsi]
0x18001cd2c  test    rax, rax
0x18001cd2f  jz      short loc_18001CD4E
0x18001cd31  mov     rcx, [rax]
0x18001cd34  test    rcx, rcx
0x18001cd37  jz      short loc_18001CD4E
0x18001cd39  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001cd3d  inc     rax
0x18001cd40  cmp     [rcx+rax*2], r15w
0x18001cd45  jnz     short loc_18001CD3D
0x18001cd47  test    rax, rax
0x18001cd4a  mov     al, 1
0x18001cd4c  jnz     short loc_18001CD51
0x18001cd4e  mov     al, r15b
0x18001cd51  mov     [rbx+141h], al
0x18001cd57  mov     [rsp+68h+var_48], 1; bool
0x18001cd5c  mov     r9b, 1; bool
0x18001cd5f  xor     r8d, r8d; struct ISWbemSecurity *
0x18001cd62  mov     rdx, r14; struct IUnknown *
0x18001cd65  mov     rcx, rbx; this
0x18001cd68  call    ?InitializeCache@CSWbemProxyCache@@AEAAXPEAUIUnknown@@PEAUISWbemSecurity@@_N2@Z; CSWbemProxyCache::InitializeCache(IUnknown *,ISWbemSecurity *,bool,bool)
0x18001cd6d  nop
0x18001cd6e  mov     rax, rbx
0x18001cd71  add     rsp, 38h
0x18001cd75  pop     r15
0x18001cd77  pop     r14
0x18001cd79  pop     rdi
0x18001cd7a  pop     rsi
0x18001cd7b  pop     rbp
0x18001cd7c  pop     rbx
0x18001cd7d  retn
```
