# CRemoteDevice::GetInterfaces(_GUID * *,ulong *)

- ea: `0x180034250`
- end: `0x18003430a`
- name: `?GetInterfaces@CRemoteDevice@@UEAAJPEAPEAU_GUID@@PEAK@Z`
- size: `186`
- prototype: `__int64 __fastcall(const void **this, struct _GUID **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000b8f8`
- `0x18001ba64`
- `0x180034250`
- `0x180047ea6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034272`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034272`

## pseudocode

```c
__int64 __fastcall CRemoteDevice::GetInterfaces(const void **this, struct _GUID **a2, unsigned int *a3)
{
  struct _GUID *v6; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax

  v6 = (struct _GUID *)CoTaskMemAlloc(16LL * *((unsigned int *)this + 34));
  *a2 = v6;
  if ( v6 )
  {
    memcpy_0(v6, this[16], 16LL * *((unsigned int *)this + 34));
    *a3 = *((_DWORD *)this + 34);
    return 0;
  }
  else
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        21,
        (unsigned int)WPP_00afc214459c30232c74a98e140fe06e_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"GUID[]");
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180034250  mov     [rsp+arg_0], rbx
0x180034255  mov     [rsp+arg_8], rsi
0x18003425a  push    rdi
0x18003425b  sub     rsp, 30h
0x18003425f  mov     rdi, rcx
0x180034262  mov     rsi, r8
0x180034265  mov     ecx, [rcx+88h]
0x18003426b  mov     rbx, rdx
0x18003426e  shl     rcx, 4; cb
0x180034272  call    cs:__imp_CoTaskMemAlloc
0x180034278  mov     [rbx], rax
0x18003427b  test    rax, rax
0x18003427e  jnz     short loc_1800342D6
0x180034280  mov     rax, cs:WPP_GLOBAL_Control
0x180034287  lea     rcx, WPP_GLOBAL_Control
0x18003428e  cmp     rax, rcx
0x180034291  jz      short loc_1800342CF
0x180034293  test    byte ptr [rax+1Ch], 8
0x180034297  jz      short loc_1800342CF
0x180034299  cmp     byte ptr [rax+19h], 2
0x18003429d  jb      short loc_1800342CF
0x18003429f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800342a4  lea     rcx, aGuid; "GUID[]"
0x1800342ab  mov     edx, 15h
0x1800342b0  mov     [rsp+38h+var_18], rcx
0x1800342b5  lea     r8, WPP_00afc214459c30232c74a98e140fe06e_Traceguids
0x1800342bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800342c3  mov     r9d, eax
0x1800342c6  mov     rcx, [rcx+10h]
0x1800342ca  call    WPP_SF_Ds
0x1800342cf  mov     eax, 8007000Eh
0x1800342d4  jmp     short loc_1800342FA
0x1800342d6  mov     r8d, [rdi+88h]
0x1800342dd  mov     rcx, rax; void *
0x1800342e0  mov     rdx, [rdi+80h]; Src
0x1800342e7  shl     r8, 4; Size
0x1800342eb  call    memcpy_0
0x1800342f0  mov     eax, [rdi+88h]
0x1800342f6  mov     [rsi], eax
0x1800342f8  xor     eax, eax
0x1800342fa  mov     rbx, [rsp+38h+arg_0]
0x1800342ff  mov     rsi, [rsp+38h+arg_8]
0x180034304  add     rsp, 30h
0x180034308  pop     rdi
0x180034309  retn
```
