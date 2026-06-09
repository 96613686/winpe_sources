# ClusApi::Cluster::CreateResourceType(wchar_t const *,wchar_t const *,wchar_t const *,ulong,ulong)

- ea: `0x18002e1c0`
- end: `0x18002e202`
- name: `?CreateResourceType@Cluster@ClusApi@@UEAAJPEB_W00KK@Z`
- size: `66`
- prototype: `__int64 __fastcall(ClusApi::Cluster *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002e1c0`

## import_xrefs

- `CLUSAPI!CreateClusterResourceTypeEx` at `0x18002e1e4`
- `CLUSAPI!CreateClusterResourceTypeEx` at `0x18002e1e4`

## string_xrefs

- `0x18002e1c8`: `cluswmiext!ClusApi::Cluster::CreateResourceType`

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
0x18002e1c0  sub     rsp, 48h
0x18002e1c4  mov     rcx, [rcx+18h]
0x18002e1c8  lea     rax, aCluswmiextClus; "cluswmiext!ClusApi::Cluster::CreateReso"...
0x18002e1cf  mov     [rsp+48h+var_18], rax
0x18002e1d4  mov     eax, [rsp+48h+arg_28]
0x18002e1d8  mov     [rsp+48h+var_20], eax
0x18002e1dc  mov     eax, [rsp+48h+arg_20]
0x18002e1e0  mov     [rsp+48h+var_28], eax
0x18002e1e4  call    cs:__imp_CreateClusterResourceTypeEx
0x18002e1eb  nop     dword ptr [rax+rax+00h]
0x18002e1f0  test    eax, eax
0x18002e1f2  jle     short loc_18002E1FC
0x18002e1f4  movzx   eax, ax
0x18002e1f7  or      eax, 80070000h
0x18002e1fc  add     rsp, 48h
0x18002e200  retn
```
