# ValuesArray::ValuesArray(Windows::Data::Json::IJsonArray *)

- ea: `0x1800123bc`
- end: `0x180012473`
- name: `??0ValuesArray@@QEAA@PEAUIJsonArray@Json@Data@Windows@@@Z`
- size: `183`
- prototype: `ValuesArray *__fastcall(ValuesArray *__hidden this, struct Windows::Data::Json::IJsonArray *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013990`

## callees

- `0x1800123bc`
- `0x180013880`
- `0x180016010`

## pseudocode

```c
ValuesArray *__fastcall ValuesArray::ValuesArray(ValuesArray *this, struct Windows::Data::Json::IJsonArray *a2)
{
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &IValuesArray::`vftable';
  *((_DWORD *)this + 8) = -607474739;
  *((_QWORD *)this + 3) = "ValuesArray";
  *((_DWORD *)this + 9) = 1;
  *((_QWORD *)this + 1) = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 2) = &CTSUnknown::`vftable'{for `CTSObject'};
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 5) = (char *)this + 8;
  *(_QWORD *)this = &ValuesArray::`vftable';
  *((_QWORD *)this + 1) = &ValuesArray::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 2) = &ValuesArray::`vftable'{for `CTSObject'};
  *((_QWORD *)this + 7) = 0;
  if ( a2 )
  {
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonArray *))(*(_QWORD *)a2 + 8LL))(a2);
    v5 = *((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = a2;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v5);
  }
  return this;
}

```

## disassembly

```asm
0x1800123bc  mov     [rsp+arg_8], rbx
0x1800123c1  push    rdi
0x1800123c2  sub     rsp, 20h
0x1800123c6  lea     rax, ??_7IValuesArray@@6B@; const IValuesArray::`vftable'
0x1800123cd  mov     rbx, rcx
0x1800123d0  mov     [rcx], rax
0x1800123d3  lea     rax, [rcx+8]
0x1800123d7  mov     dword ptr [rax+18h], 0DBCAABCDh
0x1800123de  lea     rcx, aValuesarray; "ValuesArray"
0x1800123e5  mov     [rax+10h], rcx
0x1800123e9  lea     rcx, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x1800123f0  mov     dword ptr [rax+1Ch], 1
0x1800123f7  mov     rdi, rdx
0x1800123fa  mov     [rax], rcx
0x1800123fd  lea     rcx, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180012404  mov     [rax+8], rcx
0x180012408  lea     rcx, ??_7ValuesArray@@6B@; const ValuesArray::`vftable'
0x18001240f  mov     dword ptr [rax+28h], 0
0x180012416  mov     [rax+20h], rax
0x18001241a  mov     [rbx], rcx
0x18001241d  lea     rcx, ??_7ValuesArray@@6BINonDelegatingUnknown@@@; const ValuesArray::`vftable'{for `INonDelegatingUnknown'}
0x180012424  mov     [rax], rcx
0x180012427  lea     rax, ??_7ValuesArray@@6BCTSObject@@@; const ValuesArray::`vftable'{for `CTSObject'}
0x18001242e  mov     [rbx+10h], rax
0x180012432  mov     qword ptr [rbx+38h], 0
0x18001243a  test    rdx, rdx
0x18001243d  jz      short loc_180012465
0x18001243f  mov     rax, [rdx]
0x180012442  mov     rcx, rdx
0x180012445  mov     rax, [rax+8]
0x180012449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001244e  mov     rax, [rbx+38h]
0x180012452  lea     rcx, [rsp+28h+arg_0]
0x180012457  mov     [rsp+28h+arg_0], rax
0x18001245c  mov     [rbx+38h], rdi
0x180012460  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x180012465  mov     rax, rbx
0x180012468  mov     rbx, [rsp+28h+arg_8]
0x18001246d  add     rsp, 20h
0x180012471  pop     rdi
0x180012472  retn
```
