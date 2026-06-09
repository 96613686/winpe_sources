# TSFreeCredential(_TS_CREDENTIAL *)

- ea: `0x180014100`
- end: `0x1800141b3`
- name: `?TSFreeCredential@@YAXPEAU_TS_CREDENTIAL@@@Z`
- size: `179`
- prototype: `void __fastcall(struct _TS_CREDENTIAL *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002570`
- `0x180004170`
- `0x1800053d0`

## callees

- `0x180003830`
- `0x180005ed0`
- `0x180014100`
- `0x180016650`

## import_xrefs

- `SspiCli!FreeCredentialsHandle` at `0x180014153`
- `SspiCli!FreeCredentialsHandle` at `0x180014153`
- `ntdll!RtlDeleteResource` at `0x18001415d`
- `ntdll!RtlDeleteResource` at `0x18001415d`

## pseudocode

```c
void __fastcall TSFreeCredential(struct _TS_CREDENTIAL *a1)
{
  __int64 v2; // rcx
  _BYTE *v3; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids, a1);
  if ( a1 )
  {
    if ( *((_QWORD *)a1 + 15) || *((_QWORD *)a1 + 16) )
      FreeCredentialsHandle((PCredHandle)((char *)a1 + 120));
    RtlDeleteResource((PRTL_RESOURCE)((char *)a1 + 8));
    TSFreePrimaryCredentials(*((struct _TS_PRIMARY_CREDENTIAL **)a1 + 17));
    TSFreePrimaryCredentials(*((struct _TS_PRIMARY_CREDENTIAL **)a1 + 18));
    v2 = *((unsigned int *)a1 + 40);
    v3 = (_BYTE *)*((_QWORD *)a1 + 19);
    if ( *((_DWORD *)a1 + 40) )
    {
      do
      {
        *v3++ = 0;
        --v2;
      }
      while ( v2 );
    }
    TSFree(*((void **)a1 + 19));
    TSFree(a1);
  }
}

```

## disassembly

```asm
0x180014100  push    rbx
0x180014102  sub     rsp, 20h
0x180014106  mov     rbx, rcx
0x180014109  mov     rcx, cs:WPP_GLOBAL_Control
0x180014110  lea     rax, WPP_GLOBAL_Control
0x180014117  cmp     rcx, rax
0x18001411a  jz      short loc_18001413A
0x18001411c  test    byte ptr [rcx+1Ch], 8
0x180014120  jz      short loc_18001413A
0x180014122  mov     rcx, [rcx+10h]
0x180014126  lea     r8, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids
0x18001412d  mov     edx, 14h
0x180014132  mov     r9, rbx
0x180014135  call    WPP_SF_q
0x18001413a  test    rbx, rbx
0x18001413d  jz      short loc_1800141AD
0x18001413f  lea     rcx, [rbx+78h]; phCredential
0x180014143  cmp     qword ptr [rcx], 0
0x180014147  jnz     short loc_180014153
0x180014149  cmp     qword ptr [rbx+80h], 0
0x180014151  jz      short loc_180014159
0x180014153  call    cs:__imp_FreeCredentialsHandle
0x180014159  lea     rcx, [rbx+8]; Resource
0x18001415d  call    cs:__imp_RtlDeleteResource
0x180014163  mov     rcx, [rbx+88h]; struct _TS_PRIMARY_CREDENTIAL *
0x18001416a  call    ?TSFreePrimaryCredentials@@YAJPEAU_TS_PRIMARY_CREDENTIAL@@@Z; TSFreePrimaryCredentials(_TS_PRIMARY_CREDENTIAL *)
0x18001416f  mov     rcx, [rbx+90h]; struct _TS_PRIMARY_CREDENTIAL *
0x180014176  call    ?TSFreePrimaryCredentials@@YAJPEAU_TS_PRIMARY_CREDENTIAL@@@Z; TSFreePrimaryCredentials(_TS_PRIMARY_CREDENTIAL *)
0x18001417b  mov     ecx, [rbx+0A0h]
0x180014181  mov     rax, [rbx+98h]
0x180014188  test    rcx, rcx
0x18001418b  jz      short loc_180014199
0x18001418d  mov     byte ptr [rax], 0
0x180014190  inc     rax
0x180014193  sub     rcx, 1
0x180014197  jnz     short loc_18001418D
0x180014199  mov     rcx, [rbx+98h]; void *
0x1800141a0  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x1800141a5  mov     rcx, rbx; void *
0x1800141a8  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x1800141ad  add     rsp, 20h
0x1800141b1  pop     rbx
0x1800141b2  retn
```
