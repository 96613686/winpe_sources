# HrCopyMemoryFromMarshalID(ushort,void * *,ulong *)

- ea: `0x18001a764`
- end: `0x18001a880`
- name: `?HrCopyMemoryFromMarshalID@@YAJGPEAPEAXPEAK@Z`
- size: `284`
- prototype: `__int64 __fastcall(unsigned __int16, void **, unsigned int *)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016380`
- `0x18002e1b0`
- `0x18002f230`
- `0x18002f4d0`

## callees

- `0x180002556`
- `0x18000ae04`
- `0x18001a764`
- `0x18001af64`
- `0x18001b6e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a7d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a7d3`

## pseudocode

```c
__int64 __fastcall HrCopyMemoryFromMarshalID(unsigned __int16 a1, void **a2, unsigned int *a3)
{
  unsigned int v5; // esi
  unsigned int v6; // ebp
  void *v7; // rax
  SIZE_T cb; // [rsp+50h] [rbp+8h] BYREF
  void *Src; // [rsp+68h] [rbp+20h] BYREF

  if ( !a1 || !a2 )
    return 2147942487LL;
  *a2 = 0;
  if ( a3 )
    *a3 = 0;
  Src = 0;
  LODWORD(cb) = 0;
  v5 = HrMapMarshalID(a1, &Src, (unsigned int *)&cb);
  if ( Src )
  {
    v6 = cb;
    if ( (_DWORD)cb )
    {
      v7 = CoTaskMemAlloc((unsigned int)cb);
      *a2 = v7;
      if ( v7 )
      {
        memcpy_0(v7, Src, v6);
        if ( a3 )
          *a3 = v6;
      }
      else
      {
        v5 = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            &WPP_57b06483306a3a4d34d88419a088456d_Traceguids,
            2147942414LL);
      }
      HrUnmapMarshalID(Src);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_57b06483306a3a4d34d88419a088456d_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18001a764  mov     [rsp+arg_8], rbx
0x18001a769  mov     [rsp+arg_10], rbp
0x18001a76e  push    rsi
0x18001a76f  push    rdi
0x18001a770  push    r12
0x18001a772  push    r13
0x18001a774  push    r15
0x18001a776  sub     rsp, 20h
0x18001a77a  xor     r12d, r12d
0x18001a77d  mov     rbx, r8
0x18001a780  mov     rdi, rdx
0x18001a783  test    cx, cx
0x18001a786  jz      loc_18001A864
0x18001a78c  test    rdx, rdx
0x18001a78f  jz      loc_18001A864
0x18001a795  mov     [rdx], r12
0x18001a798  test    rbx, rbx
0x18001a79b  jz      short loc_18001A7A0
0x18001a79d  mov     [r8], r12d
0x18001a7a0  lea     r8, [rsp+48h+cb]; unsigned int *
0x18001a7a5  mov     [rsp+48h+Src], r12
0x18001a7aa  lea     rdx, [rsp+48h+Src]; void **
0x18001a7af  mov     dword ptr [rsp+48h+cb], r12d
0x18001a7b4  call    ?HrMapMarshalID@@YAJGPEAPEAXPEAK@Z; HrMapMarshalID(ushort,void * *,ulong *)
0x18001a7b9  lea     r13, WPP_GLOBAL_Control
0x18001a7c0  mov     esi, eax
0x18001a7c2  cmp     [rsp+48h+Src], r12
0x18001a7c7  jz      short loc_18001A836
0x18001a7c9  mov     ebp, dword ptr [rsp+48h+cb]
0x18001a7cd  test    ebp, ebp
0x18001a7cf  jz      short loc_18001A836
0x18001a7d1  mov     ecx, ebp; cb
0x18001a7d3  call    cs:__imp_CoTaskMemAlloc
0x18001a7d9  mov     [rdi], rax
0x18001a7dc  test    rax, rax
0x18001a7df  jz      short loc_18001A7FA
0x18001a7e1  mov     rdx, [rsp+48h+Src]; Src
0x18001a7e6  mov     r8d, ebp; Size
0x18001a7e9  mov     rcx, rax; void *
0x18001a7ec  call    memcpy_0
0x18001a7f1  test    rbx, rbx
0x18001a7f4  jz      short loc_18001A82C
0x18001a7f6  mov     [rbx], ebp
0x18001a7f8  jmp     short loc_18001A82C
0x18001a7fa  mov     esi, 8007000Eh
0x18001a7ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a806  cmp     rcx, r13
0x18001a809  jz      short loc_18001A82C
0x18001a80b  test    byte ptr [rcx+1Ch], 4
0x18001a80f  jz      short loc_18001A82C
0x18001a811  mov     rcx, [rcx+10h]
0x18001a815  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x18001a81c  mov     edx, 2Ah ; '*'
0x18001a821  mov     r9d, 8007000Eh
0x18001a827  call    WPP_SF_d
0x18001a82c  mov     rcx, [rsp+48h+Src]; void *
0x18001a831  call    ?HrUnmapMarshalID@@YAJPEAX@Z; HrUnmapMarshalID(void *)
0x18001a836  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a83d  cmp     rcx, r13
0x18001a840  jz      short loc_18001A860
0x18001a842  test    byte ptr [rcx+1Ch], 10h
0x18001a846  jz      short loc_18001A860
0x18001a848  mov     rcx, [rcx+10h]
0x18001a84c  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x18001a853  mov     edx, 2Bh ; '+'
0x18001a858  mov     r9d, esi
0x18001a85b  call    WPP_SF_d
0x18001a860  mov     eax, esi
0x18001a862  jmp     short loc_18001A869
0x18001a864  mov     eax, 80070057h
0x18001a869  mov     rbx, [rsp+48h+arg_8]
0x18001a86e  mov     rbp, [rsp+48h+arg_10]
0x18001a873  add     rsp, 20h
0x18001a877  pop     r15
0x18001a879  pop     r13
0x18001a87b  pop     r12
0x18001a87d  pop     rdi
0x18001a87e  pop     rsi
0x18001a87f  retn
```
