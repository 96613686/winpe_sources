# Windows::Internal::Thumbnails::CBitmapResult::GetContentType(ushort * *)

- ea: `0x1800227f0`
- end: `0x1800228e1`
- name: `?GetContentType@CBitmapResult@Thumbnails@Internal@Windows@@UEAAJPEAPEAG@Z`
- size: `241`
- prototype: `__int64 __fastcall(Windows::Internal::Thumbnails::CBitmapResult *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800227f0`
- `0x1800228e8`
- `0x180022ad8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800228a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800228a2`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Thumbnails::CBitmapResult::GetContentType(
        Windows::Internal::Thumbnails::CBitmapResult *this,
        unsigned __int16 **a2)
{
  __int64 v4; // rax
  wchar_t **v5; // rax
  GUID *v6; // rdx
  wchar_t *v7; // r8
  __int64 v8; // rcx
  int v9; // ebx
  void *v10; // rcx
  _QWORD v12[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    v4 = *(_QWORD *)((char *)this + 52) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v4 )
      v4 = *(_QWORD *)((char *)this + 60) - *(_QWORD *)GUID_NULL.Data4;
    if ( v4 || (v9 = Windows::Internal::Thumbnails::CBitmapResult::_EnsurePropertiesResolved(this, 0), v9 >= 0) )
    {
      memset(v12, 0, 24);
      v5 = &off_18004B150;
      v6 = 0;
      while ( v5 != (wchar_t **)off_18004B210 )
      {
        v7 = v5[2];
        v8 = *(_QWORD *)v7 - *(_QWORD *)((char *)this + 52);
        if ( *(_QWORD *)v7 == *(_QWORD *)((char *)this + 52) )
          v8 = *((_QWORD *)v7 + 1) - *(_QWORD *)((char *)this + 60);
        if ( !v8 )
        {
          v6 = (GUID *)*v5;
          break;
        }
        v5 += 3;
      }
      v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
             (__int64)v12,
             (ULONGLONG)v6);
      if ( v9 < 0 )
      {
        v10 = (void *)v12[0];
      }
      else
      {
        v10 = 0;
        *a2 = (unsigned __int16 *)v12[0];
      }
      if ( v10 )
        CoTaskMemFree(v10);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800227f0  mov     [rsp+arg_0], rbx
0x1800227f5  mov     [rsp+arg_8], rsi
0x1800227fa  push    rdi
0x1800227fb  sub     rsp, 40h
0x1800227ff  mov     rsi, rdx
0x180022802  mov     rdi, rcx
0x180022805  test    rdx, rdx
0x180022808  jz      loc_1800228D3
0x18002280e  mov     qword ptr [rdx], 0
0x180022815  mov     rax, [rcx+34h]
0x180022819  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180022820  jnz     short loc_18002282D
0x180022822  mov     rax, [rcx+3Ch]
0x180022826  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18002282d  test    rax, rax
0x180022830  jz      loc_1800228C0
0x180022836  mov     [rsp+48h+var_28], 0
0x18002283f  lea     rax, off_18004B150; "image/jpeg"
0x180022846  mov     [rsp+48h+var_20], 0
0x18002284f  xor     edx, edx
0x180022851  mov     [rsp+48h+var_18], 0
0x18002285a  lea     rcx, off_18004B210
0x180022861  cmp     rax, rcx
0x180022864  jz      short loc_180022883
0x180022866  mov     r8, [rax+10h]
0x18002286a  mov     rcx, [r8]
0x18002286d  sub     rcx, [rdi+34h]
0x180022871  jnz     short loc_18002287B
0x180022873  mov     rcx, [r8+8]
0x180022877  sub     rcx, [rdi+3Ch]
0x18002287b  test    rcx, rcx
0x18002287e  jnz     short loc_1800228BA
0x180022880  mov     rdx, [rax]
0x180022883  lea     rcx, [rsp+48h+var_28]
0x180022888  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18002288d  mov     ebx, eax
0x18002288f  test    eax, eax
0x180022891  js      short loc_1800228DA
0x180022893  mov     rax, [rsp+48h+var_28]
0x180022898  xor     ecx, ecx; pv
0x18002289a  mov     [rsi], rax
0x18002289d  test    rcx, rcx
0x1800228a0  jz      short loc_1800228A8
0x1800228a2  call    cs:__imp_CoTaskMemFree
0x1800228a8  mov     rsi, [rsp+48h+arg_8]
0x1800228ad  mov     eax, ebx
0x1800228af  mov     rbx, [rsp+48h+arg_0]
0x1800228b4  add     rsp, 40h
0x1800228b8  pop     rdi
0x1800228b9  retn
0x1800228ba  add     rax, 18h
0x1800228be  jmp     short loc_18002285A
0x1800228c0  xor     edx, edx; bool
0x1800228c2  call    ?_EnsurePropertiesResolved@CBitmapResult@Thumbnails@Internal@Windows@@AEAAJ_N@Z; Windows::Internal::Thumbnails::CBitmapResult::_EnsurePropertiesResolved(bool)
0x1800228c7  mov     ebx, eax
0x1800228c9  test    eax, eax
0x1800228cb  jns     loc_180022836
0x1800228d1  jmp     short loc_1800228A8
0x1800228d3  mov     ebx, 80004003h
0x1800228d8  jmp     short loc_1800228A8
0x1800228da  mov     rcx, [rsp+48h+var_28]
0x1800228df  jmp     short loc_18002289D
```
