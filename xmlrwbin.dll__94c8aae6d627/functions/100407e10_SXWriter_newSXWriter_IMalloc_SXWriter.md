# SXWriter::newSXWriter(IMalloc *,SXWriter * *)

- ea: `0x100407e10`
- end: `0x100407eef`
- name: `?newSXWriter@SXWriter@@SAJPEAUIMalloc@@PEAPEAV1@@Z`
- size: `223`
- prototype: `__int64 __fastcall(struct IMalloc *, struct SXWriter **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x100407d50`

## callees

- `0x100406550`
- `0x100406db0`
- `0x100407050`
- `0x100407e10`
- `0x100407f00`
- `0x100414090`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXWriter::newSXWriter(struct IMalloc *a1, struct SXWriter **a2)
{
  unsigned int v4; // esi
  SXWriter *v5; // rax
  SXWriter *v6; // r14

  v4 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v5 = (SXWriter *)Base::operator new(2408, a1);
    if ( v5 )
      v6 = SXWriter::SXWriter(v5, a1);
    else
      v6 = 0;
    *a2 = v6;
    dword_100434BC0 = 0;
    RStringPtr::assign((RStringPtr *)&rspNull, (struct CStringPtr *)&cspNull);
    *((_BYTE *)v6 + 251) = 0;
    *((_QWORD *)v6 + 38) = (char *)v6 + 353;
    SXTokenTable::PushTokenTable(*((struct IMalloc **)v6 + 1), (struct SXTokenTable **)v6 + 10);
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
0x100407e10  mov     [rsp+arg_0], rbx
0x100407e15  mov     [rsp+arg_10], rsi
0x100407e1a  mov     [rsp+arg_8], rdx
0x100407e1f  push    r14
0x100407e21  sub     rsp, 40h
0x100407e25  mov     rbx, rdx
0x100407e28  mov     r14, rcx
0x100407e2b  xor     esi, esi
0x100407e2d  test    rdx, rdx
0x100407e30  jnz     short loc_100407E39
0x100407e32  mov     esi, 80004003h
0x100407e37  jmp     short loc_100407EB7
0x100407e39  mov     qword ptr [rdx], 0
0x100407e40  mov     rdx, r14
0x100407e43  mov     ecx, 968h
0x100407e48  call    ??2Base@@SAPEAX_KPEAUIMalloc@@W4NewZeroMemoryEnum@@@Z; Base::operator new(unsigned __int64,IMalloc *,NewZeroMemoryEnum)
0x100407e4d  test    rax, rax
0x100407e50  jz      short loc_100407E62
0x100407e52  mov     rdx, r14; struct IMalloc *
0x100407e55  mov     rcx, rax; this
0x100407e58  call    ??0SXWriter@@IEAA@PEAUIMalloc@@@Z; SXWriter::SXWriter(IMalloc *)
0x100407e5d  mov     r14, rax
0x100407e60  jmp     short loc_100407E65
0x100407e62  xor     r14d, r14d
0x100407e65  mov     [rbx], r14
0x100407e68  mov     cs:dword_100434BC0, 0
0x100407e72  lea     rdx, ?cspNull@@3VCStringPtr@@A; struct CStringPtr *
0x100407e79  lea     rcx, ?rspNull@@3VRStringPtr@@A; this
0x100407e80  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100407e85  mov     byte ptr [r14+0FBh], 0
0x100407e8d  lea     rax, [r14+161h]
0x100407e94  mov     [r14+130h], rax
0x100407e9b  lea     rdx, [r14+50h]; struct SXTokenTable **
0x100407e9f  mov     rcx, [r14+8]; struct IMalloc *
0x100407ea3  call    ?PushTokenTable@SXTokenTable@@SAXPEAUIMalloc@@PEAPEAV1@@Z; SXTokenTable::PushTokenTable(IMalloc *,SXTokenTable * *)
0x100407ea8  jmp     short loc_100407EB3
0x100407eaa  mov     esi, [rsp+48h+var_28]
0x100407eae  mov     rbx, [rsp+48h+arg_8]
0x100407eb3  test    esi, esi
0x100407eb5  jns     short loc_100407EDC
0x100407eb7  test    rbx, rbx
0x100407eba  jz      short loc_100407EDC
0x100407ebc  mov     rcx, [rbx]
0x100407ebf  test    rcx, rcx
0x100407ec2  jz      short loc_100407EDC
0x100407ec4  add     rcx, 10h
0x100407ec8  mov     rdx, [rcx]
0x100407ecb  mov     rax, [rdx+10h]
0x100407ecf  call    cs:__guard_dispatch_icall_fptr
0x100407ed5  mov     qword ptr [rbx], 0
0x100407edc  mov     eax, esi
0x100407ede  mov     rbx, [rsp+48h+arg_0]
0x100407ee3  mov     rsi, [rsp+48h+arg_10]
0x100407ee8  add     rsp, 40h
0x100407eec  pop     r14
0x100407eee  retn
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
