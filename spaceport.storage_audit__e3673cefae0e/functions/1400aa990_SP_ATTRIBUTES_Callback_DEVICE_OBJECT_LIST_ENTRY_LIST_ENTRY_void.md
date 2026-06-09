# SP_ATTRIBUTES::Callback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x1400aa990`
- end: `0x1400aaad2`
- name: `?Callback@SP_ATTRIBUTES@@CAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `322`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x140021df0`
- `0x1400345a0`
- `0x140067fc0`
- `0x1400a1f54`
- `0x1400a413c`
- `0x1400aa990`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400aaaa6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400aaaa6`
- `ntoskrnl!RtlStringFromGUID` at `0x1400aaa6f`
- `ntoskrnl!RtlStringFromGUID` at `0x1400aaa6f`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400aaa17`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400aaa17`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400aa9de`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400aa9de`

## pseudocode

```c
__int64 __fastcall SP_ATTRIBUTES::Callback(
        struct _DEVICE_OBJECT *a1,
        struct _LIST_ENTRY *a2,
        struct _LIST_ENTRY *a3,
        struct _ERESOURCE *a4)
{
  char v5; // bl
  __m256i *v6; // rax
  SP_CONTROL *DeviceExtension; // rbx
  PVOID RestartKey; // [rsp+30h] [rbp-19h] BYREF
  __int64 v10; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+40h] [rbp-9h] BYREF
  __m256i Guid; // [rsp+50h] [rbp+7h] BYREF

  memset(&Guid, 0, sizeof(Guid));
  while ( 2 )
  {
    v5 = 0;
    RestartKey = 0;
    SpAcquireResourceExclusive(a4 + 1);
    while ( 1 )
    {
      v6 = (__m256i *)RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)a4, &RestartKey);
      if ( !v6 )
        break;
      if ( v6->m256i_i32[6] )
      {
        Guid = *v6;
        v6->m256i_i32[6] = 0;
        if ( Guid.m256i_i32[6] == 2 )
          RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)a4, v6);
        v5 = 1;
        break;
      }
    }
    SpReleaseResourceExclusive(a4 + 1);
    if ( v5 )
    {
      if ( Guid.m256i_i32[6] == 1 )
      {
        DeviceExtension = (SP_CONTROL *)WPP_MAIN_CB.DeviceExtension;
        v10 = Guid.m256i_i64[2];
        GuidString = 0;
        if ( RtlStringFromGUID((const GUID *const)&Guid, &GuidString) >= 0 )
          SP_CONTROL::SetParameter(DeviceExtension, GuidString.Buffer, 0xBu, &v10, 8u, 0);
        RtlFreeUnicodeString(&GuidString);
      }
      else if ( Guid.m256i_i32[6] == 2 )
      {
        SP_CONTROL::DeleteParameter((SP_CONTROL *)1, (struct _GUID *)&Guid);
      }
      continue;
    }
    break;
  }
  return 0;
}

```

## disassembly

```asm
0x1400aa990  push    rbp
0x1400aa992  push    rbx
0x1400aa993  push    rsi
0x1400aa994  push    rdi
0x1400aa995  lea     rbp, [rsp-3Fh]
0x1400aa99a  sub     rsp, 88h
0x1400aa9a1  mov     rax, cs:__security_cookie
0x1400aa9a8  xor     rax, rsp
0x1400aa9ab  mov     [rbp+57h+var_30], rax
0x1400aa9af  xorps   xmm0, xmm0
0x1400aa9b2  mov     [rbp+57h+Guid.Data1], 0
0x1400aa9b9  movups  xmmword ptr [rbp+57h+Guid.Data2], xmm0
0x1400aa9bd  mov     rdi, r9
0x1400aa9c0  movups  [rbp+57h+var_40], xmm0
0x1400aa9c4  xor     bl, bl
0x1400aa9c6  mov     [rbp+57h+RestartKey], 0
0x1400aa9ce  lea     rcx, [rdi+68h]; Resource
0x1400aa9d2  call    ?SpAcquireResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpAcquireResourceExclusive(_ERESOURCE *)
0x1400aa9d7  lea     rdx, [rbp+57h+RestartKey]; RestartKey
0x1400aa9db  mov     rcx, rdi; Table
0x1400aa9de  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1400aa9e5  nop     dword ptr [rax+rax+00h]
0x1400aa9ea  test    rax, rax
0x1400aa9ed  jz      short loc_1400AAA25
0x1400aa9ef  cmp     dword ptr [rax+18h], 0
0x1400aa9f3  jz      short loc_1400AA9D7
0x1400aa9f5  movups  xmm0, xmmword ptr [rax]
0x1400aa9f8  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x1400aa9fc  movups  xmm1, xmmword ptr [rax+10h]
0x1400aaa00  movups  [rbp+57h+var_40], xmm1
0x1400aaa04  mov     dword ptr [rax+18h], 0
0x1400aaa0b  cmp     dword ptr [rbp+57h+var_40+8], 2
0x1400aaa0f  jnz     short loc_1400AAA23
0x1400aaa11  mov     rdx, rax; Buffer
0x1400aaa14  mov     rcx, rdi; Table
0x1400aaa17  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400aaa1e  nop     dword ptr [rax+rax+00h]
0x1400aaa23  mov     bl, 1
0x1400aaa25  lea     rcx, [rdi+68h]; Resource
0x1400aaa29  call    ?SpReleaseResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceExclusive(_ERESOURCE *)
0x1400aaa2e  test    bl, bl
0x1400aaa30  jz      loc_1400AAAB7
0x1400aaa36  mov     ecx, dword ptr [rbp+57h+var_40+8]
0x1400aaa39  sub     ecx, 1; this
0x1400aaa3c  jz      short loc_1400AAA51
0x1400aaa3e  cmp     ecx, 1
0x1400aaa41  jnz     short loc_1400AA9C4
0x1400aaa43  lea     rdx, [rbp+57h+Guid]; struct _GUID *
0x1400aaa47  call    ?DeleteParameter@SP_CONTROL@@QEAAJPEAU_GUID@@@Z; SP_CONTROL::DeleteParameter(_GUID *)
0x1400aaa4c  jmp     loc_1400AA9C4
0x1400aaa51  mov     rax, qword ptr [rbp+57h+var_40]
0x1400aaa55  lea     rdx, [rbp+57h+GuidString]; GuidString
0x1400aaa59  mov     rbx, cs:WPP_MAIN_CB.DeviceExtension
0x1400aaa60  lea     rcx, [rbp+57h+Guid]; Guid
0x1400aaa64  xorps   xmm0, xmm0
0x1400aaa67  mov     [rbp+57h+var_68], rax
0x1400aaa6b  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x1400aaa6f  call    cs:__imp_RtlStringFromGUID
0x1400aaa76  nop     dword ptr [rax+rax+00h]
0x1400aaa7b  test    eax, eax
0x1400aaa7d  js      short loc_1400AAAA2
0x1400aaa7f  mov     rdx, [rbp+57h+GuidString.Buffer]; unsigned __int16 *
0x1400aaa83  lea     r9, [rbp+57h+var_68]; void *
0x1400aaa87  mov     [rsp+0A0h+var_78], 0; unsigned __int8
0x1400aaa8c  mov     r8d, 0Bh; unsigned int
0x1400aaa92  mov     rcx, rbx; this
0x1400aaa95  mov     [rsp+0A0h+var_80], 8; unsigned int
0x1400aaa9d  call    ?SetParameter@SP_CONTROL@@QEAAJPEAGKPEAXKE@Z; SP_CONTROL::SetParameter(ushort *,ulong,void *,ulong,uchar)
0x1400aaaa2  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x1400aaaa6  call    cs:__imp_RtlFreeUnicodeString
0x1400aaaad  nop     dword ptr [rax+rax+00h]
0x1400aaab2  jmp     loc_1400AA9C4
0x1400aaab7  xor     eax, eax
0x1400aaab9  mov     rcx, [rbp+57h+var_30]
0x1400aaabd  xor     rcx, rsp; StackCookie
0x1400aaac0  call    __security_check_cookie
0x1400aaac5  add     rsp, 88h
0x1400aaacc  pop     rdi
0x1400aaacd  pop     rsi
0x1400aaace  pop     rbx
0x1400aaacf  pop     rbp
0x1400aaad0  retn
```
