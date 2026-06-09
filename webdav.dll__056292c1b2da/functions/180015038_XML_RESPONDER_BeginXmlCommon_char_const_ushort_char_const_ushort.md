# XML_RESPONDER::BeginXmlCommon(char const *,ushort,char const *,ushort)

- ea: `0x180015038`
- end: `0x18001512b`
- name: `?BeginXmlCommon@XML_RESPONDER@@AEAAJPEBDG0G@Z`
- size: `243`
- prototype: `__int64 __usercall@<rax>(XML_RESPONDER *__hidden this@<rcx>, const char *@<rdx>, unsigned __int16@<r8w>, const char *@<r9>, unsigned __int16)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800036a4`
- `0x18000bc4c`
- `0x18000c304`
- `0x18000e6e0`
- `0x18000f200`
- `0x180010ea0`

## callees

- `0x180015038`
- `0x18001526c`
- `0x18001c550`
- `0x180023010`

## string_xrefs

- `0x18001505c`: `<?xml version="1.0" encoding="utf-8"?>%s<D:%s xmlns:D="DAV:">%s`
- `0x1800150e1`: `text/xml`

## pseudocode

```c
int __fastcall XML_RESPONDER::BeginXmlCommon(
        XML_RESPONDER *this,
        const char *a2,
        unsigned __int16 a3,
        const char *a4,
        unsigned __int16 a5)
{
  _BYTE *v5; // rax
  struct STRA *v7; // rcx
  int result; // eax
  __int64 v11; // rax
  __int64 v12; // rax

  v5 = (_BYTE *)*((_QWORD *)this + 7);
  v7 = (XML_RESPONDER *)((char *)this + 24);
  *v5 = 0;
  *((_DWORD *)v7 + 12) = 0;
  result = SAFE_snprintf(
             v7,
             "<?xml version=\"1.0\" encoding=\"utf-8\"?>%s<D:%s xmlns:D=\"DAV:\">%s",
             *((const char **)this + 1),
             a2,
             *((const char **)this + 1));
  if ( result >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11));
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, const char *, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v11 + 24LL))(
               v11,
               a3,
               a4,
               a5,
               0,
               0,
               0);
    if ( result >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11));
      result = (*(__int64 (__fastcall **)(__int64, __int64, const char *))(*(_QWORD *)v12 + 32LL))(v12, 12, "text/xml");
      if ( result >= 0 )
      {
        result = XML_RESPONDER::Flush(this);
        if ( result >= 0 )
          *((_DWORD *)this + 24) = 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015038  mov     [rsp+arg_0], rbx
0x18001503d  mov     [rsp+arg_8], rsi
0x180015042  push    rdi
0x180015043  sub     rsp, 40h
0x180015047  mov     rax, [rcx+38h]
0x18001504b  mov     rbx, rcx
0x18001504e  add     rcx, 18h; struct STRA *
0x180015052  mov     rdi, r9
0x180015055  movzx   esi, r8w
0x180015059  mov     r9, rdx
0x18001505c  lea     rdx, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180015063  mov     byte ptr [rax], 0
0x180015066  mov     dword ptr [rcx+30h], 0
0x18001506d  mov     r8, [rbx+8]
0x180015071  mov     [rsp+48h+var_28], r8
0x180015076  call    ?SAFE_snprintf@@YAJPEAVSTRA@@PEBDZZ; SAFE_snprintf(STRA *,char const *,...)
0x18001507b  test    eax, eax
0x18001507d  js      loc_18001511B
0x180015083  mov     rcx, [rbx+58h]
0x180015087  mov     rax, [rcx]
0x18001508a  mov     rax, [rax+20h]
0x18001508e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015093  movzx   r9d, [rsp+48h+arg_20]
0x180015099  mov     r10, rax
0x18001509c  mov     [rsp+48h+var_18], 0
0x1800150a4  mov     r8, rdi
0x1800150a7  mov     [rsp+48h+var_20], 0
0x1800150b0  movzx   edx, si
0x1800150b3  mov     rcx, [rax]
0x1800150b6  mov     dword ptr [rsp+48h+var_28], 0
0x1800150be  mov     rax, [rcx+18h]
0x1800150c2  mov     rcx, r10
0x1800150c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150ca  test    eax, eax
0x1800150cc  js      short loc_18001511B
0x1800150ce  mov     rcx, [rbx+58h]
0x1800150d2  mov     rax, [rcx]
0x1800150d5  mov     rax, [rax+20h]
0x1800150d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150de  mov     r10, rax
0x1800150e1  lea     r8, aTextXml; "text/xml"
0x1800150e8  mov     r9d, 8
0x1800150ee  mov     rcx, [rax]
0x1800150f1  lea     edi, [r9-7]
0x1800150f5  lea     edx, [rdi+0Bh]
0x1800150f8  mov     dword ptr [rsp+48h+var_28], edi
0x1800150fc  mov     rax, [rcx+20h]
0x180015100  mov     rcx, r10
0x180015103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015108  test    eax, eax
0x18001510a  js      short loc_18001511B
0x18001510c  mov     rcx, rbx; this
0x18001510f  call    ?Flush@XML_RESPONDER@@AEAAJXZ; XML_RESPONDER::Flush(void)
0x180015114  test    eax, eax
0x180015116  js      short loc_18001511B
0x180015118  mov     [rbx+60h], edi
0x18001511b  mov     rbx, [rsp+48h+arg_0]
0x180015120  mov     rsi, [rsp+48h+arg_8]
0x180015125  add     rsp, 40h
0x180015129  pop     rdi
0x18001512a  retn
```
