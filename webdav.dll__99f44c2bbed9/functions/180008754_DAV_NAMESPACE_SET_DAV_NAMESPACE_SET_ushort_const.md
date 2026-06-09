# DAV_NAMESPACE_SET::DAV_NAMESPACE_SET(ushort const *)

- ea: `0x180008754`
- end: `0x1800088ce`
- name: `??0DAV_NAMESPACE_SET@@QEAA@PEBG@Z`
- size: `378`
- prototype: `DAV_NAMESPACE_SET *__fastcall(DAV_NAMESPACE_SET *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009480`
- `0x1800120e0`

## callees

- `0x180004534`
- `0x1800224c2`

## string_xrefs

- `0x180008880`: `http://www.w3.org/XML/1998/namespace`
- `0x1800088aa`: `xmlns`
- `0x18000889c`: `http://www.w3.org/2000/xmlns/`

## pseudocode

```c
DAV_NAMESPACE_SET *__fastcall DAV_NAMESPACE_SET::DAV_NAMESPACE_SET(DAV_NAMESPACE_SET *this, const unsigned __int16 *a2)
{
  _DWORD *v4; // rcx

  *(_QWORD *)this = &DAV_NAMESPACE_SET::`vftable';
  v4 = (_DWORD *)((char *)this + 8);
  v4[262] = 1;
  memset_0(v4, 0, 0x418u);
  *((_DWORD *)this + 538) = 1;
  *((_QWORD *)this + 137) = &DAV_PROPERTY_SET::`vftable';
  memset_0((char *)this + 1104, 0, 0x418u);
  *((_DWORD *)this + 540) = 0;
  *((_QWORD *)this + 133) = &DAV_WELL_KNOWN_NAMESPACE::`vftable';
  *((_QWORD *)this + 276) = &DAV_PROPERTY_SET::`vftable';
  *((_DWORD *)this + 816) = 1;
  memset_0((char *)this + 2216, 0, 0x418u);
  *((_DWORD *)this + 818) = 0;
  *((_QWORD *)this + 272) = &DAV_WELL_KNOWN_NAMESPACE::`vftable';
  *((_DWORD *)this + 1094) = 1;
  *((_QWORD *)this + 415) = &DAV_PROPERTY_SET::`vftable';
  memset_0((char *)this + 3328, 0, 0x418u);
  *((_DWORD *)this + 1096) = 0;
  *((_QWORD *)this + 411) = &DAV_WELL_KNOWN_NAMESPACE::`vftable';
  *((_DWORD *)this + 1364) = 1;
  *((_QWORD *)this + 550) = &DAV_PROPERTY_SET::`vftable';
  memset_0((char *)this + 4408, 0, 0x418u);
  *((_DWORD *)this + 1366) = 0;
  *((_QWORD *)this + 134) = L"DAV:";
  *((_QWORD *)this + 684) = a2;
  *((_QWORD *)this + 271) = L"D";
  *((_QWORD *)this + 273) = L"http://www.w3.org/XML/1998/namespace";
  *((_QWORD *)this + 410) = L"xml";
  *((_QWORD *)this + 412) = L"http://www.w3.org/2000/xmlns/";
  *((_QWORD *)this + 549) = L"xmlns";
  DAV_NAMESPACE_SET::Flush(this);
  return this;
}

```

## disassembly

```asm
0x180008754  push    rbx
0x180008756  push    rsi
0x180008757  push    rdi
0x180008758  push    r12
0x18000875a  push    r14
0x18000875c  push    r15
0x18000875e  sub     rsp, 28h
0x180008762  lea     rax, ??_7DAV_NAMESPACE_SET@@6B@; const DAV_NAMESPACE_SET::`vftable'
0x180008769  mov     rdi, rcx
0x18000876c  mov     [rcx], rax
0x18000876f  mov     rbx, rdx
0x180008772  add     rcx, 8; void *
0x180008776  mov     r15d, 418h
0x18000877c  mov     r12d, 1
0x180008782  mov     r8d, r15d; Size
0x180008785  xor     edx, edx; Val
0x180008787  mov     [rcx+418h], r12d
0x18000878e  call    memset_0
0x180008793  lea     rcx, [rdi+450h]; void *
0x18000879a  mov     r8d, r15d; Size
0x18000879d  lea     r14, ??_7DAV_PROPERTY_SET@@6B@; const DAV_PROPERTY_SET::`vftable'
0x1800087a4  mov     [rcx+418h], r12d
0x1800087ab  xor     edx, edx; Val
0x1800087ad  mov     [rdi+448h], r14
0x1800087b4  call    memset_0
0x1800087b9  mov     dword ptr [rdi+870h], 0
0x1800087c3  lea     rcx, [rdi+8A8h]; void *
0x1800087ca  lea     rsi, ??_7DAV_WELL_KNOWN_NAMESPACE@@6B@; const DAV_WELL_KNOWN_NAMESPACE::`vftable'
0x1800087d1  mov     r8d, r15d; Size
0x1800087d4  mov     [rdi+428h], rsi
0x1800087db  xor     edx, edx; Val
0x1800087dd  mov     [rdi+8A0h], r14
0x1800087e4  mov     [rcx+418h], r12d
0x1800087eb  call    memset_0
0x1800087f0  mov     dword ptr [rdi+0CC8h], 0
0x1800087fa  lea     rcx, [rdi+0D00h]; void *
0x180008801  mov     [rdi+880h], rsi
0x180008808  mov     r8d, r15d; Size
0x18000880b  xor     edx, edx; Val
0x18000880d  mov     [rcx+418h], r12d
0x180008814  mov     [rdi+0CF8h], r14
0x18000881b  call    memset_0
0x180008820  mov     dword ptr [rdi+1120h], 0
0x18000882a  lea     rcx, [rdi+1138h]; void *
0x180008831  mov     [rdi+0CD8h], rsi
0x180008838  mov     r8d, r15d; Size
0x18000883b  xor     edx, edx; Val
0x18000883d  mov     [rcx+418h], r12d
0x180008844  mov     [rdi+1130h], r14
0x18000884b  call    memset_0
0x180008850  mov     dword ptr [rdi+1558h], 0
0x18000885a  lea     rax, aDav; "DAV:"
0x180008861  mov     [rdi+430h], rax
0x180008868  mov     rcx, rdi; this
0x18000886b  lea     rax, aD_0; "D"
0x180008872  mov     [rdi+1560h], rbx
0x180008879  mov     [rdi+878h], rax
0x180008880  lea     rax, aHttpWwwW3OrgXm; "http://www.w3.org/XML/1998/namespace"
0x180008887  mov     [rdi+888h], rax
0x18000888e  lea     rax, aXml; "xml"
0x180008895  mov     [rdi+0CD0h], rax
0x18000889c  lea     rax, aHttpWwwW3Org20; "http://www.w3.org/2000/xmlns/"
0x1800088a3  mov     [rdi+0CE0h], rax
0x1800088aa  lea     rax, aXmlns_1; "xmlns"
0x1800088b1  mov     [rdi+1128h], rax
0x1800088b8  call    ?Flush@DAV_NAMESPACE_SET@@QEAAXXZ; DAV_NAMESPACE_SET::Flush(void)
0x1800088bd  mov     rax, rdi
0x1800088c0  add     rsp, 28h
0x1800088c4  pop     r15
0x1800088c6  pop     r14
0x1800088c8  pop     r12
0x1800088ca  pop     rdi
0x1800088cb  pop     rsi
0x1800088cc  pop     rbx
0x1800088cd  retn
```
