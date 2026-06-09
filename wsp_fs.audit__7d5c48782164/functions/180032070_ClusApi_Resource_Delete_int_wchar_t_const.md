# ClusApi::Resource::Delete(int,wchar_t const *)

- ea: `0x180032070`
- end: `0x1800320a4`
- name: `?Delete@Resource@ClusApi@@UEAAJHPEB_W@Z`
- size: `52`
- prototype: `__int64 __fastcall(ClusApi::Resource *__hidden this, int, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180032070`

## import_xrefs

- `CLUSAPI!DeleteClusterResourceEx` at `0x180032086`
- `CLUSAPI!DeleteClusterResourceEx` at `0x180032086`

## string_xrefs

- `0x180032078`: `cluswmiext!ClusApi::Resource::Delete`

## pseudocode

```c
__int64 __fastcall ClusApi::Resource::Delete(ClusApi::Resource *this, __int64 a2, const wchar_t *a3)
{
  __int64 v3; // rcx
  const wchar_t *v4; // rdx
  __int64 result; // rax

  v3 = *((_QWORD *)this + 7);
  v4 = L"cluswmiext!ClusApi::Resource::Delete";
  if ( a3 )
    v4 = a3;
  result = DeleteClusterResourceEx(v3, v4);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180032070  sub     rsp, 28h
0x180032074  mov     rcx, [rcx+38h]
0x180032078  lea     rdx, aCluswmiextClus_61; "cluswmiext!ClusApi::Resource::Delete"
0x18003207f  test    r8, r8
0x180032082  cmovnz  rdx, r8
0x180032086  call    cs:__imp_DeleteClusterResourceEx
0x18003208d  nop     dword ptr [rax+rax+00h]
0x180032092  test    eax, eax
0x180032094  jle     short loc_18003209E
0x180032096  movzx   eax, ax
0x180032099  or      eax, 80070000h
0x18003209e  add     rsp, 28h
0x1800320a2  retn
```
