# WldpGetSepRegistryLocation(ushort const *,ushort *,uchar *,ushort * *)

- ea: `0x180027fd0`
- end: `0x180028101`
- name: `?WldpGetSepRegistryLocation@@YAJPEBGPEAGPEAEPEAPEAG@Z`
- size: `305`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned __int8 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180028330`
- `0x180028670`
- `0x180028740`

## callees

- `0x18001f038`
- `0x1800203ec`
- `0x180026f8c`
- `0x1800271a0`
- `0x180027fd0`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18002803b`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800280a6`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002803b`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800280a6`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180028002`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180028002`

## string_xrefs

- `0x1800280bd`: `onecore\base\ngscb\wldp\dll\wldp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WldpGetSepRegistryLocation(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned __int16 **a4)
{
  unsigned int v8; // ebx
  __int64 unique_hlocal; // rax
  unsigned __int16 *v10; // r14
  int PersistedStateLocation; // eax
  int v13; // [rsp+20h] [rbp-48h]
  unsigned int v14; // [rsp+40h] [rbp-28h] BYREF
  int v15; // [rsp+44h] [rbp-24h] BYREF
  int v16[2]; // [rsp+48h] [rbp-20h] BYREF
  _BYTE v17[24]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  *(_QWORD *)v16 = 0;
  v14 = 0;
  v15 = 0;
  if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
  {
    *a3 = 0;
    *a4 = a2;
LABEL_9:
    v8 = 0;
    goto LABEL_10;
  }
  v8 = RtlGetPersistedStateLocation(a1, 0, 0, 0, 0, 0, &v14) | 0x10000000;
  if ( v8 == -1879048187 )
  {
    unique_hlocal = wil::make_unique_hlocal_nothrow<unsigned short [0]>(v17, v14);
    wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
      v16,
      unique_hlocal);
    wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(v17);
    v10 = *(unsigned __int16 **)v16;
    if ( *(_QWORD *)v16 )
    {
      PersistedStateLocation = RtlGetPersistedStateLocation(a1, 0, 0, 0, *(_QWORD *)v16, v14, &v15);
      v8 = PersistedStateLocation | 0x10000000;
      if ( PersistedStateLocation >= 0 )
      {
        *(_QWORD *)v16 = 0;
        *a4 = v10;
        wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(v16);
        *a3 = 1;
        goto LABEL_9;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA8E,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\wldp.cpp",
        (const char *)v8,
        v13);
    }
    else
    {
      v8 = -2147024882;
    }
  }
LABEL_10:
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(v16);
  return v8;
}

```

## disassembly

```asm
0x180027fd0  push    rbp
0x180027fd2  push    rbx
0x180027fd3  push    rsi
0x180027fd4  push    rdi
0x180027fd5  push    r14
0x180027fd7  push    r15
0x180027fd9  mov     rbp, rsp
0x180027fdc  sub     rsp, 68h
0x180027fe0  mov     rdi, r9
0x180027fe3  mov     rsi, r8
0x180027fe6  mov     rbx, rdx
0x180027fe9  mov     r15, rcx
0x180027fec  mov     qword ptr [rbp+var_20], 0
0x180027ff4  mov     [rbp+var_28], 0
0x180027ffb  mov     [rbp+var_24], 0
0x180028002  call    cs:__imp_RtlIsStateSeparationEnabled
0x180028008  test    al, al
0x18002800a  jnz     short loc_180028016
0x18002800c  mov     [rsi], al
0x18002800e  mov     [rdi], rbx
0x180028011  jmp     loc_1800280E7
0x180028016  lea     rax, [rbp+var_28]
0x18002801a  mov     [rsp+68h+var_38], rax
0x18002801f  mov     [rsp+68h+var_40], 0
0x180028027  mov     qword ptr [rsp+68h+var_48], 0
0x180028030  xor     r9d, r9d
0x180028033  xor     r8d, r8d
0x180028036  xor     edx, edx
0x180028038  mov     rcx, r15
0x18002803b  call    cs:__imp_RtlGetPersistedStateLocation
0x180028041  mov     ebx, eax
0x180028043  bts     ebx, 1Ch
0x180028047  cmp     ebx, 90000005h
0x18002804d  jnz     loc_1800280E9
0x180028053  mov     edx, [rbp+var_28]
0x180028056  lea     rcx, [rbp+var_18]
0x18002805a  call    ??$make_unique_hlocal_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<ushort [0]>(unsigned __int64)
0x18002805f  nop
0x180028060  mov     rdx, rax
0x180028063  lea     rcx, [rbp+var_20]
0x180028067  call    ??4?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x18002806c  nop
0x18002806d  lea     rcx, [rbp+var_18]
0x180028071  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x180028076  mov     r14, qword ptr [rbp+var_20]
0x18002807a  test    r14, r14
0x18002807d  jnz     short loc_180028086
0x18002807f  mov     ebx, 8007000Eh
0x180028084  jmp     short loc_1800280E9
0x180028086  mov     eax, [rbp+var_28]
0x180028089  lea     rcx, [rbp+var_24]
0x18002808d  mov     [rsp+68h+var_38], rcx
0x180028092  mov     [rsp+68h+var_40], eax
0x180028096  mov     qword ptr [rsp+68h+var_48], r14; int
0x18002809b  xor     r9d, r9d
0x18002809e  xor     r8d, r8d
0x1800280a1  xor     edx, edx
0x1800280a3  mov     rcx, r15
0x1800280a6  call    cs:__imp_RtlGetPersistedStateLocation
0x1800280ac  mov     ebx, eax
0x1800280ae  or      ebx, 10000000h
0x1800280b4  jge     short loc_1800280D0
0x1800280b6  mov     rcx, [rbp+30h]; this
0x1800280ba  mov     r9d, ebx; char *
0x1800280bd  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\wldp\\dll\\wldp.c"...
0x1800280c4  mov     edx, 0A8Eh; void *
0x1800280c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800280ce  jmp     short loc_1800280E9
0x1800280d0  mov     qword ptr [rbp+var_20], 0
0x1800280d8  mov     [rdi], r14
0x1800280db  lea     rcx, [rbp+var_20]
0x1800280df  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x1800280e4  mov     byte ptr [rsi], 1
0x1800280e7  xor     ebx, ebx
0x1800280e9  lea     rcx, [rbp+var_20]
0x1800280ed  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x1800280f2  mov     eax, ebx
0x1800280f4  add     rsp, 68h
0x1800280f8  pop     r15
0x1800280fa  pop     r14
0x1800280fc  pop     rdi
0x1800280fd  pop     rsi
0x1800280fe  pop     rbx
0x1800280ff  pop     rbp
0x180028100  retn
```
