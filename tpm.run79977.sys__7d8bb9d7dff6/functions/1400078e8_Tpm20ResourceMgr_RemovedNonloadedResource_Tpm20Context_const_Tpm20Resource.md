# Tpm20ResourceMgr::RemovedNonloadedResource(Tpm20Context const *,Tpm20Resource *)

- ea: `0x1400078e8`
- end: `0x140007976`
- name: `?RemovedNonloadedResource@Tpm20ResourceMgr@@AEAAXPEBVTpm20Context@@PEAVTpm20Resource@@@Z`
- size: `142`
- prototype: `void(Tpm20ResourceMgr *__hidden this, const struct Tpm20Context *, struct Tpm20Resource *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000596c`
- `0x1400080d0`
- `0x1400086a4`
- `0x140008aac`
- `0x140008bfc`

## callees

- `0x1400078e8`
- `0x140008a40`
- `0x140009224`

## pseudocode

```c
void __fastcall Tpm20ResourceMgr::RemovedNonloadedResource(
        Tpm20ResourceMgr *this,
        const struct Tpm20Context *a2,
        struct Tpm20Resource *a3)
{
  char *v3; // rax
  __int64 v5; // r8
  char **v6; // rcx
  struct Tpm20Resource *v7; // rcx
  struct Tpm20Resource **v8; // rax

  v3 = (char *)a3 + 16;
  v5 = *((_QWORD *)a3 + 2);
  if ( *(char **)(v5 + 8) != v3
    || (v6 = (char **)*((_QWORD *)v3 + 1), *v6 != v3)
    || (*v6 = (char *)v5,
        *(_QWORD *)(v5 + 8) = v6,
        v7 = *(struct Tpm20Resource **)a3,
        *(struct Tpm20Resource **)(*(_QWORD *)a3 + 8LL) != a3)
    || (v8 = (struct Tpm20Resource **)*((_QWORD *)a3 + 1), *v8 != a3) )
  {
    __fastfail(3u);
  }
  *v8 = v7;
  *((_QWORD *)v7 + 1) = v8;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      48,
      WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids,
      a2,
      *((_DWORD *)a3 + 13));
  Tpm20Context::DeleteTpm20Resource(a3);
}

```

## disassembly

```asm
0x1400078e8  push    rbx
0x1400078ea  sub     rsp, 30h
0x1400078ee  lea     rax, [r8+10h]
0x1400078f2  mov     rbx, r8
0x1400078f5  mov     r8, [rax]
0x1400078f8  mov     r9, rdx
0x1400078fb  cmp     [r8+8], rax
0x1400078ff  jnz     short loc_14000796F
0x140007901  mov     rcx, [rax+8]
0x140007905  cmp     [rcx], rax
0x140007908  jnz     short loc_14000796F
0x14000790a  mov     [rcx], r8
0x14000790d  mov     [r8+8], rcx
0x140007911  mov     rcx, [rbx]
0x140007914  cmp     [rcx+8], rbx
0x140007918  jnz     short loc_14000796F
0x14000791a  mov     rax, [rbx+8]
0x14000791e  cmp     [rax], rbx
0x140007921  jnz     short loc_14000796F
0x140007923  mov     [rax], rcx
0x140007926  mov     [rcx+8], rax
0x14000792a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140007931  lea     rax, WPP_GLOBAL_Control
0x140007938  cmp     rcx, rax
0x14000793b  jz      short loc_140007960
0x14000793d  mov     eax, [rcx+2Ch]
0x140007940  test    al, 4
0x140007942  jz      short loc_140007960
0x140007944  mov     eax, [rbx+34h]
0x140007947  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x14000794e  mov     rcx, [rcx+18h]
0x140007952  mov     edx, 30h ; '0'
0x140007957  mov     [rsp+38h+var_18], eax
0x14000795b  call    WPP_SF_qD
0x140007960  mov     rcx, rbx; struct Tpm20Resource *
0x140007963  call    ?DeleteTpm20Resource@Tpm20Context@@CAXPEAVTpm20Resource@@@Z; Tpm20Context::DeleteTpm20Resource(Tpm20Resource *)
0x140007968  add     rsp, 30h
0x14000796c  pop     rbx
0x14000796d  retn
0x14000796f  mov     ecx, 3
0x140007974  int     29h; Win8: RtlFailFast(ecx)
```
