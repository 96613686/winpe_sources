# ClusApi::Resource::Delete(int,wchar_t const *)

- ea: `0x180031040`
- end: `0x18003106d`
- name: `?Delete@Resource@ClusApi@@UEAAJHPEB_W@Z`
- size: `45`
- prototype: `__int64 __fastcall(ClusApi::Resource *__hidden this, int, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180031040`

## import_xrefs

- `CLUSAPI!DeleteClusterResourceEx` at `0x180031056`
- `CLUSAPI!DeleteClusterResourceEx` at `0x180031056`

## string_xrefs

- `0x180031048`: `cluswmiext!ClusApi::Resource::Delete`

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
0x180031040  sub     rsp, 28h
0x180031044  mov     rcx, [rcx+38h]
0x180031048  lea     rdx, aCluswmiextClus_61; "cluswmiext!ClusApi::Resource::Delete"
0x18003104f  test    r8, r8
0x180031052  cmovnz  rdx, r8
0x180031056  call    cs:__imp_DeleteClusterResourceEx
0x18003105c  test    eax, eax
0x18003105e  jle     short loc_180031068
0x180031060  movzx   eax, ax
0x180031063  or      eax, 80070000h
0x180031068  add     rsp, 28h
0x18003106c  retn
```
