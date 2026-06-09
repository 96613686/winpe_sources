# SXReader::newSXReader(IMalloc *,SXReader * *)

- ea: `0x100404170`
- end: `0x100404209`
- name: `?newSXReader@SXReader@@SAJPEAUIMalloc@@PEAPEAV1@@Z`
- size: `153`
- prototype: `__int64 __fastcall(struct IMalloc *, struct SXReader **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1004040b0`

## callees

- `0x100404170`
- `0x100404210`
- `0x1004045a0`
- `0x100406db0`
- `0x100414090`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXReader::newSXReader(struct IMalloc *a1, struct SXReader **a2)
{
  unsigned int v4; // edi
  SXReader *v5; // rax

  v4 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v5 = (SXReader *)Base::operator new(1536, a1);
    if ( v5 )
      v5 = SXReader::SXReader(v5, a1);
    *a2 = v5;
    SXReader::Initialize(v5);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v4;
}

```

## disassembly

```asm
0x100404170  mov     [rsp+arg_0], rbx
0x100404175  mov     [rsp+arg_10], rsi
0x10040417a  mov     [rsp+arg_8], rdx
0x10040417f  push    rdi
0x100404180  sub     rsp, 40h
0x100404184  mov     rbx, rdx
0x100404187  mov     rsi, rcx
0x10040418a  xor     edi, edi
0x10040418c  test    rdx, rdx
0x10040418f  jnz     short loc_100404198
0x100404191  mov     edi, 80004003h
0x100404196  jmp     short loc_1004041D6
0x100404198  mov     qword ptr [rdx], 0
0x10040419f  mov     rdx, rsi
0x1004041a2  mov     ecx, 600h
0x1004041a7  call    ??2Base@@SAPEAX_KPEAUIMalloc@@W4NewZeroMemoryEnum@@@Z; Base::operator new(unsigned __int64,IMalloc *,NewZeroMemoryEnum)
0x1004041ac  test    rax, rax
0x1004041af  jz      short loc_1004041BC
0x1004041b1  mov     rdx, rsi; struct IMalloc *
0x1004041b4  mov     rcx, rax; this
0x1004041b7  call    ??0SXReader@@IEAA@PEAUIMalloc@@@Z; SXReader::SXReader(IMalloc *)
0x1004041bc  mov     [rbx], rax
0x1004041bf  mov     rcx, rax; this
0x1004041c2  call    ?Initialize@SXReader@@QEAAXXZ; SXReader::Initialize(void)
0x1004041c7  jmp     short loc_1004041D2
0x1004041c9  mov     edi, [rsp+48h+var_28]
0x1004041cd  mov     rbx, [rsp+48h+arg_8]
0x1004041d2  test    edi, edi
0x1004041d4  jns     short loc_1004041F7
0x1004041d6  test    rbx, rbx
0x1004041d9  jz      short loc_1004041F7
0x1004041db  mov     rcx, [rbx]
0x1004041de  test    rcx, rcx
0x1004041e1  jz      short loc_1004041F7
0x1004041e3  mov     rdx, [rcx]
0x1004041e6  mov     rax, [rdx+10h]
0x1004041ea  call    cs:__guard_dispatch_icall_fptr
0x1004041f0  mov     qword ptr [rbx], 0
0x1004041f7  mov     eax, edi
0x1004041f9  mov     rbx, [rsp+48h+arg_0]
0x1004041fe  mov     rsi, [rsp+48h+arg_10]
0x100404203  add     rsp, 40h
0x100404207  pop     rdi
0x100404208  retn
0x100424620  push    rbp
0x100424622  sub     rsp, 20h
0x100424626  mov     rbp, rdx
0x100424629  mov     [rbp+38h], rcx
0x10042462d  mov     [rbp+30h], rcx
0x100424631  mov     rax, [rbp+30h]
0x100424635  mov     rcx, [rax]
0x100424638  mov     [rbp+28h], rcx
0x10042463c  mov     rax, [rbp+28h]
0x100424640  mov     eax, [rax]
0x100424642  cmp     eax, 0C0000005h
0x100424647  jz      short loc_100424679
0x100424649  add     eax, 1FFFFFFFh
0x10042464e  cmp     eax, 1
0x100424651  ja      short loc_100424669
0x100424653  mov     rax, [rbp+28h]
0x100424657  cmp     dword ptr [rax+18h], 1
0x10042465b  jnz     short loc_100424669
0x10042465d  mov     rax, [rbp+28h]
0x100424661  mov     ecx, [rax+20h]
0x100424664  mov     [rbp+20h], ecx
0x100424667  jmp     short loc_100424670
0x100424669  mov     dword ptr [rbp+20h], 8000FFFFh
0x100424670  mov     dword ptr [rbp+24h], 1
0x100424677  jmp     short loc_100424680
0x100424679  mov     dword ptr [rbp+24h], 0
0x100424680  mov     eax, [rbp+24h]
0x100424683  add     rsp, 20h
0x100424687  pop     rbp
0x100424688  retn
```
