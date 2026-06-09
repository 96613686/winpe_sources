# COfflineActivationPhoneStore::~COfflineActivationPhoneStore(void)

- ea: `0x18001e568`
- end: `0x18001e609`
- name: `??1COfflineActivationPhoneStore@@QEAA@XZ`
- size: `161`
- prototype: `void __fastcall(COfflineActivationPhoneStore *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e4f8`
- `0x18001eb40`
- `0x1800204b0`
- `0x180020e90`

## callees

- `0x18001e568`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001e57a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e597`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e5b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e5d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e5ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e57a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e597`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e5b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e5d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e5ee`

## pseudocode

```c
void __fastcall COfflineActivationPhoneStore::~COfflineActivationPhoneStore(COfflineActivationPhoneStore *this)
{
  OLECHAR *v2; // rcx
  OLECHAR *v3; // rcx
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx
  OLECHAR *v6; // rcx

  v2 = (OLECHAR *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    SysFreeString(v2);
    *((_QWORD *)this + 5) = 0;
  }
  v3 = (OLECHAR *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    SysFreeString(v3);
    *((_QWORD *)this + 4) = 0;
  }
  v4 = (OLECHAR *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    SysFreeString(v4);
    *((_QWORD *)this + 3) = 0;
  }
  v5 = (OLECHAR *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    SysFreeString(v5);
    *((_QWORD *)this + 2) = 0;
  }
  v6 = (OLECHAR *)*((_QWORD *)this + 1);
  if ( v6 )
  {
    SysFreeString(v6);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18001e568  push    rbx
0x18001e56a  sub     rsp, 20h
0x18001e56e  mov     rbx, rcx
0x18001e571  mov     rcx, [rcx+28h]; bstrString
0x18001e575  test    rcx, rcx
0x18001e578  jz      short loc_18001E58E
0x18001e57a  call    cs:__imp_SysFreeString
0x18001e581  nop     dword ptr [rax+rax+00h]
0x18001e586  mov     qword ptr [rbx+28h], 0
0x18001e58e  mov     rcx, [rbx+20h]; bstrString
0x18001e592  test    rcx, rcx
0x18001e595  jz      short loc_18001E5AB
0x18001e597  call    cs:__imp_SysFreeString
0x18001e59e  nop     dword ptr [rax+rax+00h]
0x18001e5a3  mov     qword ptr [rbx+20h], 0
0x18001e5ab  mov     rcx, [rbx+18h]; bstrString
0x18001e5af  test    rcx, rcx
0x18001e5b2  jz      short loc_18001E5C8
0x18001e5b4  call    cs:__imp_SysFreeString
0x18001e5bb  nop     dword ptr [rax+rax+00h]
0x18001e5c0  mov     qword ptr [rbx+18h], 0
0x18001e5c8  mov     rcx, [rbx+10h]; bstrString
0x18001e5cc  test    rcx, rcx
0x18001e5cf  jz      short loc_18001E5E5
0x18001e5d1  call    cs:__imp_SysFreeString
0x18001e5d8  nop     dword ptr [rax+rax+00h]
0x18001e5dd  mov     qword ptr [rbx+10h], 0
0x18001e5e5  mov     rcx, [rbx+8]; bstrString
0x18001e5e9  test    rcx, rcx
0x18001e5ec  jz      short loc_18001E602
0x18001e5ee  call    cs:__imp_SysFreeString
0x18001e5f5  nop     dword ptr [rax+rax+00h]
0x18001e5fa  mov     qword ptr [rbx+8], 0
0x18001e602  add     rsp, 20h
0x18001e606  pop     rbx
0x18001e607  retn
```
