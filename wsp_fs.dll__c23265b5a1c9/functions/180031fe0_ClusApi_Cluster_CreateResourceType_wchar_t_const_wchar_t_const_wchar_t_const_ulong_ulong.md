# ClusApi::Cluster::CreateResourceType(wchar_t const *,wchar_t const *,wchar_t const *,ulong,ulong)

- ea: `0x180031fe0`
- end: `0x180032022`
- name: `?CreateResourceType@Cluster@ClusApi@@UEAAJPEB_W00KK@Z`
- size: `66`
- prototype: `__int64 __fastcall(ClusApi::Cluster *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180031fe0`

## import_xrefs

- `CLUSAPI!CreateClusterResourceTypeEx` at `0x180032004`
- `CLUSAPI!CreateClusterResourceTypeEx` at `0x180032004`

## string_xrefs

- `0x180031fe8`: `cluswmiext!ClusApi::Cluster::CreateResourceType`

## pseudocode

```c
__int64 __fastcall ClusApi::Cluster::CreateResourceType(
        ClusApi::Cluster *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 result; // rax

  result = CreateClusterResourceTypeEx(
             *((_QWORD *)this + 3),
             a2,
             a3,
             a4,
             a5,
             a6,
             L"cluswmiext!ClusApi::Cluster::CreateResourceType");
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180031fe0  sub     rsp, 48h
0x180031fe4  mov     rcx, [rcx+18h]
0x180031fe8  lea     rax, aCluswmiextClus; "cluswmiext!ClusApi::Cluster::CreateReso"...
0x180031fef  mov     [rsp+48h+var_18], rax
0x180031ff4  mov     eax, [rsp+48h+arg_28]
0x180031ff8  mov     [rsp+48h+var_20], eax
0x180031ffc  mov     eax, [rsp+48h+arg_20]
0x180032000  mov     [rsp+48h+var_28], eax
0x180032004  call    cs:__imp_CreateClusterResourceTypeEx
0x18003200b  nop     dword ptr [rax+rax+00h]
0x180032010  test    eax, eax
0x180032012  jle     short loc_18003201C
0x180032014  movzx   eax, ax
0x180032017  or      eax, 80070000h
0x18003201c  add     rsp, 48h
0x180032020  retn
```
